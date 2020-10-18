---
title: 'Lync Server 2013: solicitar certificados para componentes perimetrales'
description: 'Lync Server 2013: solicitar certificados para componentes perimetrales.'
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
ms.openlocfilehash: 461e40921c88f26ce56141a8782ef2a04ce99667
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579016"
---
# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="6e369-103">Solicitar certificados para componentes perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e369-103">Request certificates for edge components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e369-104">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="6e369-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="6e369-105">Los certificados requeridos para admitir el acceso de usuarios externos incluyen los certificados emitidos por una entidad de certificación (CA) pública y los certificados emitidos por una CA empresarial interna:</span><span class="sxs-lookup"><span data-stu-id="6e369-105">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="6e369-106">Los certificados necesarios para la interfaz externa del servidor perimetral y el proxy inverso deben ser emitidos por una entidad de certificación pública.</span><span class="sxs-lookup"><span data-stu-id="6e369-106">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="6e369-107">Los certificados requeridos para la interfaz interna puede emitirlos tanto una CA pública como una CA empresarial interna.</span><span class="sxs-lookup"><span data-stu-id="6e369-107">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="6e369-108">Se recomienda usar una CA interna de Windows Server 2008, una CA de Windows Server 2008 R2, una CA de Windows Server 2012 o una CA de Windows Server 2012 R2 para crear estos certificados y ahorrarse en el gasto del uso de certificados públicos.</span><span class="sxs-lookup"><span data-stu-id="6e369-108">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6e369-109">El procesamiento de las solicitudes de certificado pueden tardar, en especial las solicitudes a CA públicas, por lo que deberá solicitar los certificados para sus servidores perimetrales con la suficiente anterioridad para que estén disponibles al iniciar la implementación de los componentes de servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="6e369-109">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="6e369-110">Para obtener un resumen de los requisitos de certificado para servidores perimetrales, consulte <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">requisitos de certificados para el acceso de usuarios externos en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6e369-110">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="6e369-111">Aunque puede optar por usar una CA pública para el certificado perimetral interno, se recomienda usar una CA empresarial interna para esos otros certificados, para minimizar el coste de los certificados.</span><span class="sxs-lookup"><span data-stu-id="6e369-111">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="6e369-112">Para obtener un resumen de los requisitos de certificado para servidores perimetrales, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="6e369-112">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e369-113">Al instalar un servidor perimetral, el programa de instalación incluye un asistente para certificados que facilita las tareas de solicitud, asignación e instalación de certificados, tal como se describe en la sección <A href="lync-server-2013-set-up-edge-certificates.md">configurar certificados perimetrales para Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="6e369-113">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="6e369-114">Si desea solicitar certificados antes de instalar un servidor perimetral (por ejemplo, para ahorrar tiempo durante la implementación real de los componentes del servidor perimetral), puede hacerlo con servidores internos siempre que garantice que los certificados son exportables y contienen todos los nombres alternativos de sujeto necesarios.</span><span class="sxs-lookup"><span data-stu-id="6e369-114">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="6e369-115">Esta documentación no indica los procedimientos de uso de los servidores internos para solicitar certificados.</span><span class="sxs-lookup"><span data-stu-id="6e369-115">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="6e369-116">Solicitar certificados a una CA pública</span><span class="sxs-lookup"><span data-stu-id="6e369-116">Request certificates from a public CA</span></span>

<span data-ttu-id="6e369-117">La implementación del servidor perimetral requiere un único certificado público para las interfaces externas de los servidores perimetrales, que se usa para el servicio perimetral de acceso, el servicio perimetral de conferencia web y para el servicio de autenticación A/V.</span><span class="sxs-lookup"><span data-stu-id="6e369-117">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="6e369-118">Este certificado debe tener una clave privada exportable para asegurarse de que el servicio de autenticación A/V usa las mismas claves en todos los servidores perimetrales de un grupo.</span><span class="sxs-lookup"><span data-stu-id="6e369-118">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="6e369-119">El proxy inverso, que se usa con Microsoft Internet Security and Acceleration (ISA) Server 2006 o Microsoft Forefront Threat Management Gateway 2010, también requiere un certificado público.</span><span class="sxs-lookup"><span data-stu-id="6e369-119">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="6e369-120">Solicitar certificados a una CA empresarial interna</span><span class="sxs-lookup"><span data-stu-id="6e369-120">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="6e369-p106">Los certificados necesarios para la interfaz perimetral interna pueden proceder de una entidad de certificación pública o de una entidad de certificación interna. Se puede usar una entidad de certificación empresarial interna para que el costo de los certificados sea menor. Si la organización tiene implementada una entidad de certificación interna, es la que debe emitir los certificados para la red perimetral interna. Si se recurre a una entidad de certificación empresarial interna para obtener los certificados internos, el costo de los certificados se verá reducido.</span><span class="sxs-lookup"><span data-stu-id="6e369-p106">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA. You can use an internal enterprise CA to help minimize the cost of certificates. If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA. Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="6e369-125">Para obtener un resumen de los requisitos de certificado para los componentes perimetrales, consulte [Certificate Requirements for external User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="6e369-125">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="6e369-126">Para obtener información detallada sobre cómo usar una CA pública para obtener certificados, consulte [solicitar certificados para componentes perimetrales en Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span><span class="sxs-lookup"><span data-stu-id="6e369-126">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="6e369-127">Para obtener más información sobre cómo solicitar, instalar y asignar certificados, consulte [configurar los certificados perimetrales para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6e369-127">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

