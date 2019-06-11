---
title: 'Lync Server 2013: Plan para certificados de servidores perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 737e0845b4b9966accd8c450b8a300b4f1bb128e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="cc53d-102">Plan para certificados de servidores perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc53d-102">Plan for Edge Server certificates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc53d-103">_**Última modificación del tema:** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="cc53d-103">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="cc53d-104">La creación de certificados para Edge se ha simplificado en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cc53d-104">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="cc53d-105">**Diagrama de flujo de certificados para el servidor perimetral**</span><span class="sxs-lookup"><span data-stu-id="cc53d-105">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="cc53d-106">![a5fc20db-7ced-4364-b577-6a709a8367cd] (images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="cc53d-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="cc53d-107">Cree un único certificado público, asegúrese de que tiene una clave privada exportable definida para el certificado y asígnela a las siguientes interfaces externas de servidor perimetral con el Asistente para certificados:</span><span class="sxs-lookup"><span data-stu-id="cc53d-107">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cc53d-108">Los certificados comodín no se admiten en Lync Server, excepto cuando se usan para resumir las direcciones URL simples a través del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="cc53d-108">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="cc53d-109">Debe definir distintos nombres alternativos de sujeto (San) para cada nombre de dominio SIP, servicio perimetral de conferencias web, servicio perimetral A/V y dominio XMPP ofrecido por su implementación.</span><span class="sxs-lookup"><span data-stu-id="cc53d-109">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="cc53d-110">Introducida en Lync Server 2013, el almacenamiento provisional de certificados de autenticación de audio y vídeo con antelación a la fecha de expiración del certificado actual requiere una planificación adicional.</span><span class="sxs-lookup"><span data-stu-id="cc53d-110">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="cc53d-111">En lugar de un certificado con varios propósitos para la interfaz de borde externo, necesitará dos certificados, uno asignado al servicio perimetral de acceso y el servicio perimetral de conferencia Web, y un certificado para el servicio perimetral de a/V.</span><span class="sxs-lookup"><span data-stu-id="cc53d-111">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="cc53d-112">Para obtener más información, consulte <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">almacenamiento provisional de certificados AV y OAuth en Lync Server 2013 uso de-roll en Set-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="cc53d-112">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cc53d-113">En el caso de un grupo de servidores perimetrales, exporte el certificado con la clave privada a cada servidor perimetral y asigne el certificado a cada servicio de servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="cc53d-113">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="cc53d-114">Haga lo mismo para el certificado de servidor perimetral interno, exporte el certificado con la clave privada y asignándole la asignación a cada interfaz de borde interno.</span><span class="sxs-lookup"><span data-stu-id="cc53d-114">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="cc53d-115">Asegúrese de que tiene asignada una clave privada exportable para el certificado</span><span class="sxs-lookup"><span data-stu-id="cc53d-115">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="cc53d-116">Servicio perimetral de acceso (denominado **SIP perimetral de acceso externo** en el Asistente para certificados)</span><span class="sxs-lookup"><span data-stu-id="cc53d-116">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="cc53d-117">Servicio perimetral de conferencias web (denominado **borde de conferencias web externo** en el Asistente para certificados)</span><span class="sxs-lookup"><span data-stu-id="cc53d-117">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="cc53d-118">Servicio de autenticación a/V (denominado **borde a/v externo** en el Asistente para certificados)</span><span class="sxs-lookup"><span data-stu-id="cc53d-118">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="cc53d-119">Crear un único certificado interno con una clave privada exportable, cópielo y asígnelo a cada una de las interfaces internas del servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="cc53d-119">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="cc53d-120">Servidor perimetral (denominado interno de la **arista** en el Asistente para certificados)</span><span class="sxs-lookup"><span data-stu-id="cc53d-120">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cc53d-121">Es posible usar certificados diferentes y diferentes para cada servicio de servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="cc53d-121">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="cc53d-122">Una buena razón para elegir certificados independientes es si desea usar la nueva característica de certificados sucesivos para el certificado de servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="cc53d-122">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="cc53d-123">En el caso de esta característica, se recomienda disociar el certificado de servicio perimetral A/V del servicio perimetral de acceso y el servicio perimetral de conferencia Web.</span><span class="sxs-lookup"><span data-stu-id="cc53d-123">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="cc53d-124">Si elige solicitar, adquirir y asignar certificados independientes para cada servicio, debe solicitar que se pueda exportar la clave privada para el servicio perimetral A/V (nuevamente, esto es en realidad el servicio de autenticación A/V) y asignar el mismo certificado a la A/V Interfaz externa de Edge en cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="cc53d-124">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc53d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc53d-125">See Also</span></span>


[<span data-ttu-id="cc53d-126">Almacenamiento provisional de certificados AV y OAuth en Lync Server 2013 usar-Roll en Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="cc53d-126">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="cc53d-127">Cambios en Lync Server 2013 que afectan a la planificación del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="cc53d-127">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

