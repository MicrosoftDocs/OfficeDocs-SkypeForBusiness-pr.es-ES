---
title: 'Lync Server 2013: amenazas comunes de seguridad en el entorno informático de hoy día'
description: 'Lync Server 2013: amenazas de seguridad comunes en informática moderna.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47284d91ea9f14e3bafadb1a285f6e98d9ea7ded
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576996"
---
# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="cd269-103">Amenazas de seguridad comunes en el entorno informático de hoy día</span><span class="sxs-lookup"><span data-stu-id="cd269-103">Common security threats in modern day computing</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd269-104">_**Última modificación del tema:** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="cd269-104">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="cd269-105">Dado que Lync Server 2013 es un sistema de comunicaciones de clase empresarial, debe tener en cuenta los ataques de seguridad comunes que podrían afectar a su infraestructura y comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="cd269-105">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="cd269-106">Ataque de clave comprometida</span><span class="sxs-lookup"><span data-stu-id="cd269-106">Compromised-Key Attack</span></span>

<span data-ttu-id="cd269-107">Una clave es un número o código secreto que se usa para cifrar, descifrar o validar información secreta.</span><span class="sxs-lookup"><span data-stu-id="cd269-107">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information.</span></span> <span data-ttu-id="cd269-108">Hay dos claves confidenciales en uso en la infraestructura de clave pública (PKI) que se deben tener en cuenta:.</span><span class="sxs-lookup"><span data-stu-id="cd269-108">There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="cd269-109">La clave privada que tiene cada titular del certificado</span><span class="sxs-lookup"><span data-stu-id="cd269-109">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="cd269-110">La clave de sesión que se usa después de una identificación correcta y el intercambio de claves de sesión por parte de los socios de comunicación</span><span class="sxs-lookup"><span data-stu-id="cd269-110">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="cd269-111">Un ataque de clave comprometida se produce cuando el atacante determina la clave privada o la clave de sesión.</span><span class="sxs-lookup"><span data-stu-id="cd269-111">A compromised-key attack occurs when the attacker determines the private key or the session key.</span></span> <span data-ttu-id="cd269-112">Cuando el atacante logra determinar la clave, la usa para descifrar los datos cifrados sin que lo sepa el remitente de los datos.</span><span class="sxs-lookup"><span data-stu-id="cd269-112">When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="cd269-113">Lync Server 2013 usa las características de PKI del sistema operativo Windows Server para proteger los datos clave usados para el cifrado de las conexiones de seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="cd269-113">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="cd269-114">Las claves usadas para el cifrado de medios se intercambian a través de conexiones TLS.</span><span class="sxs-lookup"><span data-stu-id="cd269-114">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="cd269-115">Ataque por denegación de servicio de la red</span><span class="sxs-lookup"><span data-stu-id="cd269-115">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="cd269-116">El *ataque por denegación de servicio* se produce cuando el atacante evita el uso normal de la red y la función de los usuarios válidos.</span><span class="sxs-lookup"><span data-stu-id="cd269-116">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users.</span></span> <span data-ttu-id="cd269-117">Esto se realiza cuando el atacante inunda el servicio con solicitudes legítimas que saturan el uso del servicio por parte de usuarios legítimos.</span><span class="sxs-lookup"><span data-stu-id="cd269-117">This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users.</span></span> <span data-ttu-id="cd269-118">Mediante el uso de un ataque por denegación de servicio, el atacante puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd269-118">By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="cd269-119">Enviar datos no válidos a las aplicaciones y los servicios que se ejecutan en la red que sufre el ataque para interrumpir su funcionamiento normal.</span><span class="sxs-lookup"><span data-stu-id="cd269-119">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="cd269-120">Enviar una gran cantidad de tráfico, lo que sobrecarga el sistema hasta que deja de responder o responde lentamente a las solicitudes legítimas.</span><span class="sxs-lookup"><span data-stu-id="cd269-120">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="cd269-121">Ocultar las pruebas de los ataques.</span><span class="sxs-lookup"><span data-stu-id="cd269-121">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="cd269-122">Impedir que los usuarios obtengan acceso a los recursos de la red.</span><span class="sxs-lookup"><span data-stu-id="cd269-122">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="cd269-123">Espionaje (espionaje, espionaje)</span><span class="sxs-lookup"><span data-stu-id="cd269-123">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="cd269-124">El *espionaje* puede producirse cuando un atacante obtiene acceso a la ruta de datos en una red y tiene la capacidad de supervisar y leer el tráfico.</span><span class="sxs-lookup"><span data-stu-id="cd269-124">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic.</span></span> <span data-ttu-id="cd269-125">También se denomina *rastreo* o *supervisión*.</span><span class="sxs-lookup"><span data-stu-id="cd269-125">This is also called *sniffing* or *snooping*.</span></span> <span data-ttu-id="cd269-126">Si el tráfico se produce como texto sin formato, el atacante puede leerlo cuando obtiene acceso a la ruta.</span><span class="sxs-lookup"><span data-stu-id="cd269-126">If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path.</span></span> <span data-ttu-id="cd269-127">Un ejemplo es un ataque que se realiza al controlar un enrutador de la ruta de acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="cd269-127">An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="cd269-128">La recomendación y configuración predeterminadas para el tráfico dentro de Microsoft Lync Server 2013 es usar TLS mutua (MTLS) entre los servidores de confianza y TLS del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="cd269-128">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="cd269-129">Esta medida protectora haría muy difícil o imposible lograr un ataque en el período en el que se produce una conversación determinada.</span><span class="sxs-lookup"><span data-stu-id="cd269-129">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="cd269-130">TLS autentica a todos los participantes y cifra todo el tráfico.</span><span class="sxs-lookup"><span data-stu-id="cd269-130">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="cd269-131">Esto no impide la interceptación, pero el atacante no puede leer el tráfico a menos se interrumpa el cifrado.</span><span class="sxs-lookup"><span data-stu-id="cd269-131">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="cd269-132">El protocolo de retransmisión NAT (TURN) no exige que el tráfico se cifre y que la información que envía está protegida por la integridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="cd269-132">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity.</span></span> <span data-ttu-id="cd269-133">Aunque está abierto a espionaje, la información que envía (es decir, las direcciones IP y el puerto) se puede extraer directamente con solo mirar las direcciones de origen y de destino de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="cd269-133">Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets.</span></span> <span data-ttu-id="cd269-134">El servicio perimetral A/V garantiza que los datos sean válidos mediante la comprobación de la integridad del mensaje con la clave derivada de algunos elementos, incluida una contraseña de TORNEAdo, que nunca se envía en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="cd269-134">The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text.</span></span> <span data-ttu-id="cd269-135">Si se usa el protocolo seguro en tiempo real (SRTP), también se cifra el tráfico de medios.</span><span class="sxs-lookup"><span data-stu-id="cd269-135">If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="cd269-136">Suplantación de identidad (suplantación de dirección IP)</span><span class="sxs-lookup"><span data-stu-id="cd269-136">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="cd269-137">La *suplantación de identidad* se produce cuando el atacante determina y usa una dirección IP de una red, un equipo o un componente de red sin tener autorización para ello.</span><span class="sxs-lookup"><span data-stu-id="cd269-137">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="cd269-138">En este tipo de ataque, el atacante actúa como si fuese la entidad que hubiera identificado la dirección IP en un caso normal.</span><span class="sxs-lookup"><span data-stu-id="cd269-138">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="cd269-139">En el contexto de Microsoft Lync Server 2013, esta situación entra en juego solo si un administrador ha hecho lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd269-139">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="cd269-140">Ha configurado conexiones compatibles únicamente con el Protocolo de control de transmisión (TCP) (lo cual no se recomienda porque las comunicaciones TCP no están cifradas).</span><span class="sxs-lookup"><span data-stu-id="cd269-140">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="cd269-141">Ha marcado las direcciones IP de esas conexiones como hosts de confianza.</span><span class="sxs-lookup"><span data-stu-id="cd269-141">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="cd269-142">Este es un problema menor para las conexiones TLS (Seguridad de la capa de transporte), puesto que TLS autentica todas las partes y cifra todo el tráfico.</span><span class="sxs-lookup"><span data-stu-id="cd269-142">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="cd269-143">El uso de TLS evita que un atacante suplante las direcciones IP en una conexión concreta (por ejemplo, conexiones Mutual TLS).</span><span class="sxs-lookup"><span data-stu-id="cd269-143">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="cd269-144">Pero un atacante todavía podría suplantar la dirección del servidor DNS que usa Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd269-144">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="cd269-145">No obstante, puesto que la autenticación en Lync se realiza con certificados, un atacante no tendrá un certificado válido necesario para suplantar a una de las partes de la comunicación.</span><span class="sxs-lookup"><span data-stu-id="cd269-145">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="cd269-146">Ataque de tipo "Man in the middle"</span><span class="sxs-lookup"><span data-stu-id="cd269-146">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="cd269-147">Un ataque de tipo "Man in the middle" se produce cuando un atacante desvía la comunicación entre dos usuarios a través del equipo del atacante sin que lo sepan esos dos usuarios.</span><span class="sxs-lookup"><span data-stu-id="cd269-147">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="cd269-148">El atacante puede supervisar y leer el tráfico antes de enviarlo al destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="cd269-148">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="cd269-149">Sin darse cuenta, todos los usuarios que participan en la comunicación envían tráfico al atacante y reciben tráfico del mismo pensando que la comunicación se produce únicamente con el usuario previsto.</span><span class="sxs-lookup"><span data-stu-id="cd269-149">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="cd269-150">Esto puede suceder si un atacante modifica los Servicios de dominio de Active Directory para agregar su servidor como un servidor de confianza o modifica el Sistema de nombres de dominio (DNS) para que los clientes se conecten al servidor a través del atacante.</span><span class="sxs-lookup"><span data-stu-id="cd269-150">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="cd269-151">Un ataque de tipo "Man in the Middle" también puede producirse con el tráfico de medios entre dos clientes.</span><span class="sxs-lookup"><span data-stu-id="cd269-151">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="cd269-152">Sin embargo, en Microsoft Lync Server 2013 uso compartido de audio, vídeo y aplicaciones punto a punto, las secuencias se cifran con SRTP, usando claves criptográficas que se negocian entre los homólogos que usan el protocolo de inicio de sesión (SIP) a través de TLS.</span><span class="sxs-lookup"><span data-stu-id="cd269-152">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="cd269-153">Los servidores como los de conversaciones en grupo utilizan HTTPS para mejorar la seguridad del tráfico web.</span><span class="sxs-lookup"><span data-stu-id="cd269-153">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="cd269-154">Ataque de reproducción RTP</span><span class="sxs-lookup"><span data-stu-id="cd269-154">RTP Replay Attack</span></span>

<span data-ttu-id="cd269-155">Un *ataque de reproducción* se produce cuando se intercepta y retransmite una transmisión de medios válida entre dos partes con fines malintencionados.</span><span class="sxs-lookup"><span data-stu-id="cd269-155">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes.</span></span> <span data-ttu-id="cd269-156">SRTP, usado en conexión con un protocolo de señalización segura, protege las transmisiones de estos ataques al permitir que el receptor tenga un índice de los paquetes RTP ya recibidos y pueda comparar cada paquete nuevo con los que figuran en dicho índice.</span><span class="sxs-lookup"><span data-stu-id="cd269-156">SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="cd269-157">Solicitado</span><span class="sxs-lookup"><span data-stu-id="cd269-157">Spim</span></span>

<span data-ttu-id="cd269-158">*Spim* es mensajes instantáneos comerciales no solicitados o solicitudes de suscripción de presencia.</span><span class="sxs-lookup"><span data-stu-id="cd269-158">*Spim* is unsolicited commercial instant messages or presence subscription requests.</span></span> <span data-ttu-id="cd269-159">Si bien estos mensajes por sí mismos no son un peligro para la seguridad de la red, son como mínimo molestos, pueden reducir la disponibilidad y la productividad de los recursos, y podrían llegar a poner en peligro la red.</span><span class="sxs-lookup"><span data-stu-id="cd269-159">While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network.</span></span> <span data-ttu-id="cd269-160">Un ejemplo de ello es el caso de usuarios que se envían solicitudes no deseadas entre sí.</span><span class="sxs-lookup"><span data-stu-id="cd269-160">An example of this is users spimming each other by sending requests.</span></span> <span data-ttu-id="cd269-161">Los usuarios pueden bloquearse entre sí para evitarlo, pero con la federación, si se establece un ataque coordinado de este tipo, puede ser difícil de solucionar a menos que se deshabilite la federación para el asociado.</span><span class="sxs-lookup"><span data-stu-id="cd269-161">Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="cd269-162">Virus y gusanos</span><span class="sxs-lookup"><span data-stu-id="cd269-162">Viruses and Worms</span></span>

<span data-ttu-id="cd269-163">Un *virus* es una unidad de código cuyo propósito es reproducir unidades de código similares adicionales.</span><span class="sxs-lookup"><span data-stu-id="cd269-163">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units.</span></span> <span data-ttu-id="cd269-164">Los virus necesitan un host (como un archivo, un correo electrónico o un programa) para poder funcionar.</span><span class="sxs-lookup"><span data-stu-id="cd269-164">To work, a virus needs a host, such as a file, email, or program.</span></span> <span data-ttu-id="cd269-165">Un *gusano* es una unidad de código cuyo propósito es reproducir más unidades de código similares, pero no necesita un host.</span><span class="sxs-lookup"><span data-stu-id="cd269-165">A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host.</span></span> <span data-ttu-id="cd269-166">Los virus y los gusanos suelen aparecer principalmente durante las transferencias de archivo entre clientes o cuando otros usuarios envían direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="cd269-166">Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users.</span></span> <span data-ttu-id="cd269-167">Si hay un virus en su equipo, podrá, por ejemplo, usar su identidad y enviar mensajes instantáneos en su nombre.</span><span class="sxs-lookup"><span data-stu-id="cd269-167">If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="cd269-168">Información de identificación personal</span><span class="sxs-lookup"><span data-stu-id="cd269-168">Personally Identifiable Information</span></span>

<span data-ttu-id="cd269-169">Microsoft Lync Server 2013 tiene el potencial de divulgar información a través de una red pública que pueda estar vinculada a un individuo.</span><span class="sxs-lookup"><span data-stu-id="cd269-169">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="cd269-170">Dicha información se puede desglosar en dos categorías:</span><span class="sxs-lookup"><span data-stu-id="cd269-170">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="cd269-171">**Datos de presencia mejorados** Los datos de presencia mejorados son información que un usuario puede elegir para compartir o no a través de un vínculo a un socio federado o con contactos dentro de una organización.</span><span class="sxs-lookup"><span data-stu-id="cd269-171">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="cd269-172">Estos datos no se comparten con los usuarios de una red de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="cd269-172">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="cd269-173">Las directivas de cliente y otras opciones de configuración del cliente pueden otorgar algún tipo de control al administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="cd269-173">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="cd269-174">En Lync Server 2013, se puede configurar el modo de privacidad de presencia mejorada para un usuario individual para impedir que los usuarios de Lync que no se encuentran en la lista de contactos del usuario vean la información de presencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="cd269-174">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="cd269-175">El modo de privacidad de presencia mejorada no impide que los usuarios de Microsoft Office Communicator 2007 y Microsoft Office Communicator 2007 R2 vean la información de presencia de un usuario.</span><span class="sxs-lookup"><span data-stu-id="cd269-175">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="cd269-176">Para obtener más información, consulte [what's New for clients in Lync server 2013](lync-server-2013-what-s-new-for-clients.md) en la documentación de introducción y [configuración del modo de privacidad de presencia mejorada en Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="cd269-176">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="cd269-177">**Datos obligatorios** Los datos obligatorios son necesarios para el correcto funcionamiento del servidor o el cliente y no están bajo el control de la administración del cliente o del sistema.</span><span class="sxs-lookup"><span data-stu-id="cd269-177">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="cd269-178">Se trata de información que es necesaria en un servidor o una red para el enrutamiento, el mantenimiento de estados y la señalización.</span><span class="sxs-lookup"><span data-stu-id="cd269-178">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="cd269-179">En las tablas siguientes se enumeran los datos que se exponen a través de una red pública.</span><span class="sxs-lookup"><span data-stu-id="cd269-179">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="cd269-180">Datos de presencia ampliada</span><span class="sxs-lookup"><span data-stu-id="cd269-180">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd269-181">Datos que se han divulgado</span><span class="sxs-lookup"><span data-stu-id="cd269-181">Data Disclosed</span></span></th>
<th><span data-ttu-id="cd269-182">Configuración posible</span><span class="sxs-lookup"><span data-stu-id="cd269-182">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd269-183">Datos personales</span><span class="sxs-lookup"><span data-stu-id="cd269-183">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="cd269-184">Nombre, puesto, compañía, dirección de correo electrónico, zona horaria</span><span class="sxs-lookup"><span data-stu-id="cd269-184">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd269-185">Números de teléfono</span><span class="sxs-lookup"><span data-stu-id="cd269-185">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="cd269-186">Trabajo, Móvil, Particular</span><span class="sxs-lookup"><span data-stu-id="cd269-186">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd269-187">Información de calendario</span><span class="sxs-lookup"><span data-stu-id="cd269-187">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="cd269-188">Información de disponibilidad, aviso de fuera de la oficina, detalles de la reunión (para los usuarios que tienen acceso a su calendario)</span><span class="sxs-lookup"><span data-stu-id="cd269-188">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd269-189">Estado de presencia</span><span class="sxs-lookup"><span data-stu-id="cd269-189">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="cd269-190">Ausente, Disponible, No disponible, No molestar, No conectado</span><span class="sxs-lookup"><span data-stu-id="cd269-190">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="cd269-191">Datos obligatorios</span><span class="sxs-lookup"><span data-stu-id="cd269-191">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd269-192">Datos que se han divulgado</span><span class="sxs-lookup"><span data-stu-id="cd269-192">Data Disclosed</span></span></th>
<th><span data-ttu-id="cd269-193">Información de ejemplo</span><span class="sxs-lookup"><span data-stu-id="cd269-193">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd269-194">Dirección IP</span><span class="sxs-lookup"><span data-stu-id="cd269-194">IP Address</span></span></p></td>
<td><p><span data-ttu-id="cd269-195">Dirección real del equipo o dirección traducida</span><span class="sxs-lookup"><span data-stu-id="cd269-195">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd269-196">URI del SIP</span><span class="sxs-lookup"><span data-stu-id="cd269-196">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="cd269-197">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cd269-197">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

