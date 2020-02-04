---
title: 'Lync Server 2013: Solicitar certificados para componentes perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 096603b48e6a3636a397c4abf7c19c2b4237f132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="e648b-102">Solicitar certificados para componentes perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e648b-102">Request certificates for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e648b-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="e648b-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="e648b-104">Los certificados necesarios para admitir el acceso de usuarios externos incluyen certificados emitidos por una entidad de certificación (CA) pública y certificados emitidos por una entidad de certificación empresarial interna:</span><span class="sxs-lookup"><span data-stu-id="e648b-104">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="e648b-105">Los certificados necesarios para la interfaz externa del servidor perimetral y el proxy inverso deben ser emitidos por una entidad de certificación pública.</span><span class="sxs-lookup"><span data-stu-id="e648b-105">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="e648b-106">Los certificados necesarios para la interfaz interna pueden ser emitidos por una entidad de certificación pública o por una entidad de certificación empresarial interna.</span><span class="sxs-lookup"><span data-stu-id="e648b-106">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="e648b-107">Recomendamos usar una CA interna de Windows Server 2008, Windows Server 2008 R2 CA, Windows Server 2012 CA o Windows Server 2012 R2 CA para crear estos certificados y ahorrar al gasto de usar certificados públicos.</span><span class="sxs-lookup"><span data-stu-id="e648b-107">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e648b-108">Puede demorar el proceso de procesar las solicitudes de certificado, especialmente las de las entidades de certificación públicas, por lo que debe solicitar certificados para los servidores perimetrales lo suficientemente pronto como para asegurarse de que estén disponibles al iniciar la implementación de los componentes del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="e648b-108">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="e648b-109">Para obtener un resumen de los requisitos de certificado para servidores perimetrales, consulte <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">requisitos de certificados para el acceso de usuarios externos en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e648b-109">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e648b-110">Aunque puede elegir usar una CA pública para el certificado de contorno interno, le recomendamos que use una CA de empresa interna para esos otros certificados para minimizar el costo de los certificados.</span><span class="sxs-lookup"><span data-stu-id="e648b-110">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="e648b-111">Para obtener un resumen de los requisitos de certificado para servidores perimetrales, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e648b-111">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e648b-112">Al instalar un servidor perimetral, el programa de instalación incluye un asistente de certificados que facilita las tareas de solicitar, asignar e instalar certificados, como se describe en la sección <A href="lync-server-2013-set-up-edge-certificates.md">configurar certificados perimetrales para Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="e648b-112">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="e648b-113">Si desea solicitar certificados antes de instalar un servidor perimetral (por ejemplo, para ahorrar tiempo durante la implementación real de los componentes del servidor perimetral), puede hacerlo con servidores internos siempre que se asegure de que los certificados son exportables y contienen todos los se necesitan nombres alternativos de asunto.</span><span class="sxs-lookup"><span data-stu-id="e648b-113">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="e648b-114">En esta documentación no se proporcionan procedimientos para usar servidores internos con el fin de solicitar certificados.</span><span class="sxs-lookup"><span data-stu-id="e648b-114">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="e648b-115">Solicitar certificados de una entidad de certificación pública</span><span class="sxs-lookup"><span data-stu-id="e648b-115">Request certificates from a public CA</span></span>

<span data-ttu-id="e648b-116">La implementación de su servidor perimetral requiere un único certificado público para las interfaces externas de los servidores perimetrales, que se usa para el servicio perimetral de acceso, el servicio perimetral de conferencias web y para el servicio de autenticación A/V.</span><span class="sxs-lookup"><span data-stu-id="e648b-116">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="e648b-117">Este certificado debe tener una clave privada exportable para asegurarse de que el servicio de autenticación A/V use las mismas claves en todos los servidores perimetrales de un grupo.</span><span class="sxs-lookup"><span data-stu-id="e648b-117">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="e648b-118">El proxy inverso, que se usa con Microsoft Internet Security and Acceleration (ISA) Server 2006 o Microsoft Forefront Threat Management Gateway 2010, también requiere un certificado público.</span><span class="sxs-lookup"><span data-stu-id="e648b-118">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="e648b-119">Solicitar certificados de una CA de empresa interna</span><span class="sxs-lookup"><span data-stu-id="e648b-119">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="e648b-120">Los certificados necesarios para la interfaz de borde interno pueden ser emitidos por una entidad de certificación pública (CA) o una CA interna.</span><span class="sxs-lookup"><span data-stu-id="e648b-120">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA.</span></span> <span data-ttu-id="e648b-121">Puede usar una entidad de certificación empresarial interna para ayudar a minimizar el costo de los certificados.</span><span class="sxs-lookup"><span data-stu-id="e648b-121">You can use an internal enterprise CA to help minimize the cost of certificates.</span></span> <span data-ttu-id="e648b-122">Si su organización tiene una CA interna implementada, la entidad de certificación interna debe emitir los certificados para el contorno interno.</span><span class="sxs-lookup"><span data-stu-id="e648b-122">If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA.</span></span> <span data-ttu-id="e648b-123">El uso de una CA de empresa interna para certificados internos puede reducir el costo de los certificados.</span><span class="sxs-lookup"><span data-stu-id="e648b-123">Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="e648b-124">Para obtener un resumen de los requisitos de certificado para los componentes de Edge, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e648b-124">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="e648b-125">Para obtener más información sobre cómo usar una CA pública para obtener certificados, consulte [solicitar certificados para componentes de Edge en Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span><span class="sxs-lookup"><span data-stu-id="e648b-125">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="e648b-126">Para obtener más información sobre cómo solicitar, instalar y asignar certificados, consulte [configurar certificados perimetrales para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="e648b-126">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

