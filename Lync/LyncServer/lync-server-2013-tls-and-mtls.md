---
title: 'Lync Server 2013: TLS y MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06938cfb6c37a84de5256feb6e4b370eb36f3702
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="7294f-102">TLS y MTLS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7294f-102">TLS and MTLS for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7294f-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="7294f-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="7294f-104">Los protocolos de Seguridad de la capa de transporte (TLS) y Seguridad de la capa de transporte mutua (MTLS) ofrecen comunicaciones cifradas y autenticación de extremos en Internet.</span><span class="sxs-lookup"><span data-stu-id="7294f-104">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="7294f-105">Microsoft Lync Server 2013 usa estos dos protocolos para crear la red de servidores de confianza y garantizar que todas las comunicaciones a través de esa red están cifradas.</span><span class="sxs-lookup"><span data-stu-id="7294f-105">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="7294f-106">Todas las comunicaciones SIP entre los servidores se llevan a cabo a través de MTLS.</span><span class="sxs-lookup"><span data-stu-id="7294f-106">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="7294f-107">Las comunicaciones SIP entre el cliente y el servidor se realizan a través de TLS.</span><span class="sxs-lookup"><span data-stu-id="7294f-107">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="7294f-108">TLS permite a los usuarios, mediante el software cliente, autenticar los servidores de Lync Server 2013 a los que se conectan.</span><span class="sxs-lookup"><span data-stu-id="7294f-108">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="7294f-109">En una conexión TLS, el cliente solicita un certificado válido del servidor.</span><span class="sxs-lookup"><span data-stu-id="7294f-109">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="7294f-110">Para que sea válido, el certificado debe haber sido emitido por una CA que también sea de confianza para el cliente y el nombre DNS del servidor debe coincidir con el nombre DNS del certificado.</span><span class="sxs-lookup"><span data-stu-id="7294f-110">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="7294f-111">Si el certificado es válido, el cliente usa la clave pública del certificado para cifrar las claves de cifrado simétricas que se utilizarán para la comunicación, de modo que solo el propietario original del certificado puede usar su clave privada para descifrar el contenido de la comunicación.</span><span class="sxs-lookup"><span data-stu-id="7294f-111">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="7294f-112">La conexión resultante es fiable y desde ese punto no es desafiada por otros servidores o clientes fiables.</span><span class="sxs-lookup"><span data-stu-id="7294f-112">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="7294f-113">En este contexto, SSL, tal como se usa con los servicios web, se puede asociar como basada en TLS.</span><span class="sxs-lookup"><span data-stu-id="7294f-113">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="7294f-114">Las conexiones entre servidores dependen de MTLS para la autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="7294f-114">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="7294f-115">En una conexión MTLS, el servidor de origen de un mensaje y el que lo recibe intercambian certificados procedentes de una CA de confianza para ambos.</span><span class="sxs-lookup"><span data-stu-id="7294f-115">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="7294f-116">Los certificados permiten a los servidores demostrarse mutuamente sus identidades.</span><span class="sxs-lookup"><span data-stu-id="7294f-116">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="7294f-117">En implementaciones de Lync Server 2013, los certificados emitidos por la CA de empresa que se encuentren durante el período de validez y que no hayan sido revocados por la entidad emisora de certificados son considerados automáticamente por todos los clientes y servidores internos, ya que todos los miembros de un dominio de Active Directory confiar en la entidad emisora de certificados de empresa en ese dominio.</span><span class="sxs-lookup"><span data-stu-id="7294f-117">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="7294f-118">En los escenarios de federación, ambos socios federados deben confiar en la CA que emite los certificados.</span><span class="sxs-lookup"><span data-stu-id="7294f-118">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="7294f-119">Si así lo desea, cada socio puede utilizar una CA diferente, siempre y cuando el otro socio también confíe en esa CA.</span><span class="sxs-lookup"><span data-stu-id="7294f-119">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="7294f-120">La manera más fácil de lograr esa confianza es configurar los servidores perimetrales para que el certificado de la CA raíz del socio figure entre sus CA raíz de confianza, o bien usar una CA de otro fabricante en la que confíen ambas partes.</span><span class="sxs-lookup"><span data-stu-id="7294f-120">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="7294f-121">TLS y MTLS ayudan a evitar los ataques de interceptación y de tipo "Man in the middle".</span><span class="sxs-lookup"><span data-stu-id="7294f-121">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="7294f-122">En los ataques de tipo "Man in the middle", el atacante enruta las comunicaciones entre dos entidades de red a través del equipo del atacante sin que lo sepa ninguna de esas entidades.</span><span class="sxs-lookup"><span data-stu-id="7294f-122">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="7294f-123">TLS y la especificación 2013 de Lync Server de servidores de confianza (solo las especificadas en el generador de topologías) reducen el riesgo de un ataque de intermediario parcialmente en el nivel de aplicación mediante el cifrado de extremo a extremo coordinado con el cifrado de clave pública entre los dos puntos de conexión, un atacante tendría que tener un certificado válido y confiable con la clave privada correspondiente y se emitió para el nombre del servicio al que se comunica el cliente para descifrar la comunicación.</span><span class="sxs-lookup"><span data-stu-id="7294f-123">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="7294f-124">En todo caso, usted deberá seguir buenas prácticas de seguridad en su infraestructura de red (en este caso, DNS empresarial).</span><span class="sxs-lookup"><span data-stu-id="7294f-124">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="7294f-125">Lync Server 2013 supone que el servidor DNS es de confianza de la misma forma en que se confía en los controladores de dominio y los catálogos globales, pero DNS ofrece un nivel de protección contra ataques de usurpación de DNS evitando que el servidor de un atacante responda correctamente a un solicitud para el nombre falso.</span><span class="sxs-lookup"><span data-stu-id="7294f-125">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="7294f-126">En la siguiente ilustración se muestra en un nivel superior cómo Lync Server 2013 usa MTLS para crear una red de servidores de confianza.</span><span class="sxs-lookup"><span data-stu-id="7294f-126">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="7294f-127">**Conexiones de confianza en una red de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="7294f-127">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="7294f-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="7294f-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

