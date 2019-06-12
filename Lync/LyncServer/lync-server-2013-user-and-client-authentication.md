---
title: 'Lync Server 2013: autenticación de usuario y de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 052c65bad805dff0d993cbf8533593c1f12915a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="79d81-102">Autenticación de usuarios y clientes para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79d81-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79d81-103">_**Última modificación del tema:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="79d81-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="79d81-104">Un usuario de confianza es aquel cuyas credenciales han sido autenticadas por un servidor de confianza en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79d81-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="79d81-105">Este servidor suele ser un servidor Standard Edition, Enterprise Edition o director.</span><span class="sxs-lookup"><span data-stu-id="79d81-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="79d81-106">Lync Server 2013 confía en los servicios de dominio de Active Directory como el único repositorio back-end de confianza de credenciales de usuario.</span><span class="sxs-lookup"><span data-stu-id="79d81-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="79d81-107">La autenticación consiste en proporcionar credenciales de usuario a un servidor de confianza.</span><span class="sxs-lookup"><span data-stu-id="79d81-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="79d81-108">Lync Server 2013 usa los siguientes protocolos de autenticación, según el estado y la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="79d81-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="79d81-109">**Protocolo de seguridad MIT Kerberos versión 5** para usuarios internos con credenciales de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="79d81-109">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="79d81-110">Kerberos requiere conectividad de cliente con los servicios de dominio de Active Directory, motivo por el cual no se puede usar para autenticar clientes fuera del firewall de la empresa.</span><span class="sxs-lookup"><span data-stu-id="79d81-110">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="79d81-111">**Protocolo NTLM** para usuarios con credenciales de Active Directory que se conectan desde un extremo fuera del Firewall corporativo.</span><span class="sxs-lookup"><span data-stu-id="79d81-111">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="79d81-112">El servicio perimetral de acceso pasa las solicitudes de inicio de sesión a un director, si está presente, o a un servidor front-end para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="79d81-112">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="79d81-113">El servicio perimetral de acceso en sí no realiza ninguna autenticación.</span><span class="sxs-lookup"><span data-stu-id="79d81-113">The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79d81-114">El protocolo NTLM ofrece una protección contra ataques más débil que la de Kerberos, por lo que algunas organizaciones minimizan el uso de NTLM.</span><span class="sxs-lookup"><span data-stu-id="79d81-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="79d81-115">Como resultado, el acceso a Lync Server 2013 puede estar restringido a interno o a los clientes conectados a través de una conexión VPN o DirectAccess.</span><span class="sxs-lookup"><span data-stu-id="79d81-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="79d81-p106">**Protocolo de autenticación** implícita para los usuarios denominados anónimos. Los usuarios anónimos son usuarios externos que no tienen credenciales de Active Directory reconocidas, pero que han recibido una invitación a una conferencia local y tienen una clave de conferencia válida. La autenticación implícita no se utiliza para otras interacciones del cliente.</span><span class="sxs-lookup"><span data-stu-id="79d81-p106">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="79d81-119">La autenticación de Lync Server 2013 consta de dos fases:</span><span class="sxs-lookup"><span data-stu-id="79d81-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="79d81-120">Se establece una asociación de seguridad entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="79d81-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="79d81-p107">El cliente y el servidor utilizan la asociación de seguridad existente para firmar los mensajes que envían y comprobar los que reciben. Cuando la autenticación está habilitada en el servidor, no se aceptan los mensajes no autenticados de un cliente.</span><span class="sxs-lookup"><span data-stu-id="79d81-p107">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="79d81-p108">La confianza en un usuario se adjunta a cada mensaje que procede del usuario, no a la identidad del usuario. El servidor comprueba cada mensaje para determinar si las credenciales de usuario son válidas. Si lo son, no solo el primer servidor en recibir el mensaje no lo desafía, sino que tampoco lo hacen los demás servidores de la nube de servidores de confianza.</span><span class="sxs-lookup"><span data-stu-id="79d81-p108">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="79d81-126">Los usuarios con credenciales válidas emitidas por un socio federado son de confianza pero, de manera opcional, algunas restricciones adicionales impiden que disfruten de todos los privilegios otorgados a los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="79d81-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="79d81-127">Los protocolos ICE y TURN también usan el desafío de autenticación implícita que se describe en la RFC del IETF referente a TURN.</span><span class="sxs-lookup"><span data-stu-id="79d81-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="79d81-128">Los certificados de cliente proporcionan una forma alternativa para que los usuarios puedan ser autenticados por Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79d81-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="79d81-129">En vez de proporcionar un nombre de usuario y una contraseña, los usuarios cuentan con un certificado y una clave privada correspondiente al certificado necesario para resolver un desafío criptográfico.</span><span class="sxs-lookup"><span data-stu-id="79d81-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="79d81-130">(Este certificado debe tener un nombre de asunto o un nombre alternativo de asunto que identifique al usuario y debe ser emitido por una CA raíz en la que confían los servidores que ejecutan Lync Server 2013, que está dentro del período de validez del certificado y que no se ha revocado). Para ser autenticado, los usuarios solo tienen que escribir un número de identificación personal (PIN).</span><span class="sxs-lookup"><span data-stu-id="79d81-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="79d81-131">Los certificados son particularmente útiles para teléfonos y otros dispositivos que ejecutan Microsoft Lync 2013 Phone Edition, en los que es difícil introducir un nombre de usuario o una contraseña.</span><span class="sxs-lookup"><span data-stu-id="79d81-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

