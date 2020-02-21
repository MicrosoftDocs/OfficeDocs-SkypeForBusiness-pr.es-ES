---
title: 'Lync Server 2013: requisitos de configuración para el proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13026da5515615610c960fe4648d5c58f64f99fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="12691-102">Requisitos de configuración para el proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12691-102">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12691-103">_**Última modificación del tema:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="12691-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="12691-104">Lync Server 2013 impone algunos requisitos en las comunicaciones del cliente externo que luego se pasan a los servicios web externos hospedados en el director, el grupo de directores, el servidor front-end o el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="12691-104">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="12691-105">El proxy inverso también es responsable de publicar el servidor de Office Web Apps, si ofrece conferencias a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="12691-105">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="12691-106">Lync Server 2013 no especifica un proxy inverso concreto que debe usar.</span><span class="sxs-lookup"><span data-stu-id="12691-106">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="12691-107">Lync Server 2013 solo define los requisitos operativos que el proxy inverso debe poder hacer.</span><span class="sxs-lookup"><span data-stu-id="12691-107">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="12691-108">Normalmente, el proxy inverso que ya ha implementado en su infraestructura puede cumplir los requisitos.</span><span class="sxs-lookup"><span data-stu-id="12691-108">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="12691-109">Requisitos de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="12691-109">Reverse Proxy Requirements</span></span>

<span data-ttu-id="12691-110">Las operaciones funcionales que Lync Server 2013 espera que realice un proxy inverso son:</span><span class="sxs-lookup"><span data-stu-id="12691-110">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="12691-111">Use la capa de sockets seguros (SSL) y la seguridad de la capa de transporte (TLS) implementada mediante certificados adquiridos de una entidad de certificación pública para conectarse a los servicios web externos publicados del Director, el grupo de servidores de Director, el servidor front-end o el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="12691-111">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="12691-112">El director y el servidor front-end pueden estar en un grupo de carga equilibrada mediante equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="12691-112">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="12691-113">Posibilidad de publicar sitios Web internos con certificados para cifrado o publicarlos a través de un medio sin cifrar, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="12691-113">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="12691-114">Puede publicar un sitio web hospedado internamente de forma externa mediante un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="12691-114">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="12691-115">Puede publicar todo el contenido del sitio web hospedado.</span><span class="sxs-lookup"><span data-stu-id="12691-115">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="12691-116">De forma predeterminada, puede usar la \*\* / \*\* Directiva, que es reconocida por la mayoría de los servidores web para indicar "publicar todo el contenido en el servidor Web".</span><span class="sxs-lookup"><span data-stu-id="12691-116">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="12691-117">También puede modificar la Directiva, por ejemplo, **/Uwca/\***, que significa "publicar todo el contenido en el directorio virtual Ucwa".</span><span class="sxs-lookup"><span data-stu-id="12691-117">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="12691-118">Debe poder configurarse para requerir conexiones de capa de sockets seguros (SSL) y seguridad de la capa de transporte (TLS) con clientes que soliciten contenido desde un sitio Web publicado.</span><span class="sxs-lookup"><span data-stu-id="12691-118">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="12691-119">Debe aceptar certificados con entradas de nombre alternativo de sujeto (SAN).</span><span class="sxs-lookup"><span data-stu-id="12691-119">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="12691-120">Debe poder permitir el enlace de un certificado a un agente de escucha o a una interfaz a través de la cual se resolverá el FQDN de servicios web externos.</span><span class="sxs-lookup"><span data-stu-id="12691-120">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="12691-121">Las configuraciones de la escucha son preferibles a las interfaces.</span><span class="sxs-lookup"><span data-stu-id="12691-121">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="12691-122">Se pueden configurar varios agentes de escucha en una sola interfaz.</span><span class="sxs-lookup"><span data-stu-id="12691-122">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="12691-123">Debe permitir la configuración de la administración del encabezado de host.</span><span class="sxs-lookup"><span data-stu-id="12691-123">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="12691-124">A menudo, el encabezado de host original enviado por el cliente que realiza la solicitud debe pasar de forma transparente, en lugar de ser modificado por el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="12691-124">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="12691-125">Puentes de tráfico SSL y TLS desde un puerto definido externamente (por ejemplo, TCP 443) a otro puerto definido (por ejemplo, TCP 4443).</span><span class="sxs-lookup"><span data-stu-id="12691-125">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="12691-126">El proxy inverso puede descifrar el paquete en su recepción y, a continuación, volver a cifrar el paquete en el envío.</span><span class="sxs-lookup"><span data-stu-id="12691-126">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="12691-127">Puentes de tráfico TCP no cifrado de un puerto (por ejemplo, TCP 80) a otro (por ejemplo, TCP 8080).</span><span class="sxs-lookup"><span data-stu-id="12691-127">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="12691-128">Permitir la configuración de la autenticación NTLM, o aceptarla, sin autenticación ni autenticación de paso a través.</span><span class="sxs-lookup"><span data-stu-id="12691-128">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

