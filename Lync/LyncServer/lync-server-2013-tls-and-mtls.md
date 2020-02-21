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
ms.openlocfilehash: 39c3d9dbaeb4c630445b832ab8f220c209461837
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="1b6c0-102">TLS y MTLS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b6c0-102">TLS and MTLS for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b6c0-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="1b6c0-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="1b6c0-104">Los protocolos de seguridad de la capa de transporte (TLS) y seguridad de la capa de transporte mutua (MTLS) proporcionan comunicaciones cifradas y autenticación de extremo en Internet.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-104">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="1b6c0-105">Microsoft Lync Server 2013 usa estos dos protocolos para crear la red de servidores de confianza y garantizar que todas las comunicaciones a través de esa red están cifradas.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-105">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="1b6c0-106">Todas las comunicaciones SIP entre servidores se producen a través de MTLS.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-106">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="1b6c0-107">Las comunicaciones SIP del cliente al servidor se producen a través de TLS.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-107">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="1b6c0-108">TLS permite a los usuarios, mediante su software cliente, autenticar los servidores de Lync Server 2013 a los que se conectan.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-108">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="1b6c0-109">En una conexión TLS, el cliente solicita un certificado válido del servidor.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-109">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="1b6c0-110">Para que sea válido, el certificado debe haber sido emitido por una entidad de certificación que también sea de confianza para el cliente y el nombre DNS del servidor debe coincidir con el nombre DNS del certificado.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-110">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="1b6c0-111">Si el certificado es válido, el cliente usa la clave pública del certificado para cifrar las claves de cifrado simétricas que se van a usar para la comunicación, por lo que solo el propietario original del certificado puede usar su clave privada para descifrar el contenido de la comunicación.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-111">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="1b6c0-112">La conexión resultante es de confianza y desde ese punto no es cuestionada por otros servidores o clientes de confianza.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-112">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="1b6c0-113">Dentro de este contexto, la capa de sockets seguros (SSL), tal como se usa con los servicios Web, se puede asociar como basada en TLS.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-113">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="1b6c0-114">Las conexiones de servidor a servidor se basan en MTLS para la autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-114">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="1b6c0-115">En una conexión MTLS, el servidor que originó un mensaje y el servidor que los recibe intercambian certificados de una entidad de certificación de confianza mutua.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-115">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="1b6c0-116">Los certificados demuestran la identidad de cada servidor en el otro.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-116">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="1b6c0-117">En las implementaciones de Lync Server 2013, los certificados emitidos por la CA de empresa que están durante el período de validez y no revocados por la CA emisora se consideran automáticamente válidos para todos los clientes y servidores internos, ya que todos los miembros de un dominio de Active Directory Confíe en la entidad de certificación empresarial de ese dominio.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-117">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="1b6c0-118">En los escenarios federados, los dos socios federados deben confiar en la entidad emisora de certificados.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-118">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="1b6c0-119">Cada socio puede usar una entidad de certificación diferente, si lo desea, siempre que el otro asociado también confíe en esa CA.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-119">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="1b6c0-120">Esta confianza es más sencilla para los servidores perimetrales que tienen el certificado de CA raíz del asociado en sus entidades de certificación raíz de confianza o mediante el uso de una entidad de certificación de terceros en la que confían ambas partes.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-120">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="1b6c0-121">TLS y MTLS ayudan a evitar el espionaje y los ataques de intermediario.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-121">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="1b6c0-122">En un ataque de tipo "Man in the Middle", el atacante redirige las comunicaciones entre dos entidades de red a través del equipo del atacante sin el conocimiento de ninguna de las partes.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-122">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="1b6c0-123">TLS y Lync Server 2013 especificación de servidores de confianza (sólo los especificados en el generador de topologías) mitiga el riesgo de un ataque de intermediario parcialmente en el nivel de aplicación mediante el cifrado de un extremo a otro coordinado mediante la criptografía de clave pública entre los dos puntos de conexión, y un atacante tendría que tener un certificado válido y de confianza con la clave privada correspondiente y que se haya emitido para el nombre del servicio al que el cliente se comunica para descifrar la comunicación.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-123">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="1b6c0-124">Sin embargo, en última instancia, debe seguir los procedimientos de seguridad de la infraestructura de red (en este caso, el DNS corporativo).</span><span class="sxs-lookup"><span data-stu-id="1b6c0-124">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="1b6c0-125">Lync Server 2013 presupone que el servidor DNS es de confianza de la misma manera que los controladores de dominio y los catálogos globales son de confianza, pero DNS proporciona un nivel de protección contra ataques de secuestro de DNS al impedir que el servidor del atacante responda correctamente a un solicitud al nombre falso.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-125">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="1b6c0-126">En la figura siguiente se muestra a alto nivel cómo Lync Server 2013 usa MTLS para crear una red de servidores de confianza.</span><span class="sxs-lookup"><span data-stu-id="1b6c0-126">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="1b6c0-127">**Conexiones de confianza en una red de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="1b6c0-127">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="1b6c0-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="1b6c0-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

