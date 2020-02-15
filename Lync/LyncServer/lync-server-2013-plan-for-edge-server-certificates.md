---
title: 'Lync Server 2013: planear los certificados del servidor perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b70d9635b253c793170ff11373f6d063f0f46c81
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="f8414-102">Planeación de certificados de servidor perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8414-102">Plan for Edge Server certificates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8414-103">_**Última modificación del tema:** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="f8414-103">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="f8414-104">La creación de certificados para Edge se ha simplificado en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8414-104">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="f8414-105">**Diagrama de flujo de certificados para servidores perimetrales**</span><span class="sxs-lookup"><span data-stu-id="f8414-105">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="f8414-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="f8414-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="f8414-107">Cree un certificado público único, compruebe que tiene una clave privada exportable definida para el certificado y asígnela a las interfaces externas del servidor perimetral usando el asistente para certificados:</span><span class="sxs-lookup"><span data-stu-id="f8414-107">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f8414-108">Los certificados comodín no son compatibles con Lync Server, excepto cuando se usan para resumir las direcciones URL sencillas a través del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f8414-108">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="f8414-109">Debe definir distintos nombres alternativos de sujeto (San) para cada nombre de dominio SIP, servicio perimetral de conferencia Web, servicio perimetral A/V y dominio XMPP ofrecido por la implementación.</span><span class="sxs-lookup"><span data-stu-id="f8414-109">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f8414-110">Presentada en Lync Server 2013, el almacenamiento provisional de certificados de autenticación de audio y vídeo antes de la fecha de expiración del certificado actual requiere una planificación adicional.</span><span class="sxs-lookup"><span data-stu-id="f8414-110">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="f8414-111">En lugar de un certificado con varios propósitos para la interfaz perimetral externa, necesitará dos certificados, uno asignado al servicio perimetral de acceso y el servicio perimetral de conferencia Web, y un certificado para el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="f8414-111">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="f8414-112">Para obtener más información, consulte staging de los <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">certificados AV y OAuth en Lync Server 2013 usando-Roll en Set-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="f8414-112">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f8414-113">En el caso de un grupo de servidores perimetrales, exporte el certificado con la clave privada a cada servidor perimetral y asigne el certificado a cada servicio de servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="f8414-113">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="f8414-114">Haga lo mismo con el certificado del servidor perimetral interno, exporte el certificado con la clave privada y asigne a cada interfaz perimetral interna.</span><span class="sxs-lookup"><span data-stu-id="f8414-114">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="f8414-115">Compruebe que se ha asignado la clave privada exportable al certificado</span><span class="sxs-lookup"><span data-stu-id="f8414-115">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="f8414-116">Servicio perimetral de acceso (denominado servidor **perimetral de acceso SIP externo** en el Asistente para certificados)</span><span class="sxs-lookup"><span data-stu-id="f8414-116">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="f8414-117">Servicio perimetral de conferencia web (denominado servidor **perimetral externo de conferencia web** en el Asistente para certificados)</span><span class="sxs-lookup"><span data-stu-id="f8414-117">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="f8414-118">Servicio de autenticación A/V (denominado **Servidor perimetral externo de A/V** en el asistente para certificados)</span><span class="sxs-lookup"><span data-stu-id="f8414-118">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="f8414-119">Cree un solo certificado interno con una clave privada exportable, cópielo y asígnelo a cada una de las siguientes interfaces internas de servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="f8414-119">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="f8414-120">Servidor perimetral (denominado **Servidor perimetral interno** en el asistente para certificados)</span><span class="sxs-lookup"><span data-stu-id="f8414-120">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f8414-121">Es posible usar certificados separados y distintos para cada servicio de servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="f8414-121">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="f8414-122">Una buena razón para elegir certificados separados es si desea usar la nueva característica de certificado rodante para el certificado del servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="f8414-122">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="f8414-123">En el caso de esta característica, se recomienda desacoplar el certificado del servicio perimetral A/V del servicio perimetral de acceso y del servicio perimetral de conferencia Web.</span><span class="sxs-lookup"><span data-stu-id="f8414-123">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="f8414-124">Si elige solicitar, adquirir y asignar certificados independientes para cada servicio, debe solicitar que la clave privada sea exportable para el servicio perimetral A/V (de nuevo, esto es en realidad el servicio de autenticación A/V) y asignar el mismo certificado a la interfaz perimetral externa a/V en cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="f8414-124">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8414-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8414-125">See Also</span></span>


[<span data-ttu-id="f8414-126">Almacenamiento provisional de certificados AV y OAuth en Lync Server 2013 usando-Roll en Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="f8414-126">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="f8414-127">Cambios en Lync Server 2013 que afectan a la planeación del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="f8414-127">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

