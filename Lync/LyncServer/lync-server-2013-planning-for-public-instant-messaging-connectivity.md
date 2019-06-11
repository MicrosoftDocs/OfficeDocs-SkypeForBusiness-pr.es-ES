---
title: 'Lync Server 2013: planeamiento de la conectividad de mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4432484fbd6056d51a38090a18dbe106851d7c0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="88626-102">Planeamiento de la conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88626-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88626-103">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="88626-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="88626-104">La conectividad de mensajería instantánea pública es una clase de Federación y está configurada para permitir a los usuarios internos y externos de Lync Server 2013 agregar contactos de cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="88626-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="88626-105">Contactos de Messenger</span><span class="sxs-lookup"><span data-stu-id="88626-105">Messenger contacts</span></span>

  - <span data-ttu-id="88626-106">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="88626-106">Yahoo\!</span></span> <span data-ttu-id="88626-107">contactos</span><span class="sxs-lookup"><span data-stu-id="88626-107">contacts</span></span>

  - <span data-ttu-id="88626-108">Contactos de America Online (AOL)</span><span class="sxs-lookup"><span data-stu-id="88626-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="88626-109">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de la conectividad de mensajería instantánea pública de Microsoft Lync (PIC USL) ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="88626-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="88626-110">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="88626-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="88626-111">Messenger hasta la fecha de cierre del servicio.</span><span class="sxs-lookup"><span data-stu-id="88626-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="88626-112">Una fecha de fin de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="88626-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="88626-113">ha sido anunciado.</span><span class="sxs-lookup"><span data-stu-id="88626-113">has been announced.</span></span> <span data-ttu-id="88626-114">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="88626-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="88626-115">El PIC USL es una licencia por usuario y por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="88626-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="88626-116">Mensajería.</span><span class="sxs-lookup"><span data-stu-id="88626-116">Messenger.</span></span> <span data-ttu-id="88626-117">La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el cual no se renovará.</span><span class="sxs-lookup"><span data-stu-id="88626-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="88626-118">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="88626-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="88626-119">La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="88626-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="88626-120">La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas a través de la mensajería instantánea y la voz.</span><span class="sxs-lookup"><span data-stu-id="88626-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="88626-121">Esta clase de Federación requiere las siguientes consideraciones de planeación:</span><span class="sxs-lookup"><span data-stu-id="88626-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="88626-122">Los usuarios de Windows Live Messenger pueden tener una comunicación visual o de audio de punto a punto con los usuarios de Lync Server 2013, además de la mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="88626-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="88626-123">Los servidores perimetrales deben cumplir con requisitos de puerto y protocolo específicos.</span><span class="sxs-lookup"><span data-stu-id="88626-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="88626-124">Para obtener más información, consulte [determinar el firewall externo a/V y los requisitos de puerto para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88626-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="88626-125">La mensajería instantánea de Yahoo no tiene requisitos únicos, excepto los que normalmente se usan en la planificación y la implementación del servidor perimetral típico que proporciona la Federación.</span><span class="sxs-lookup"><span data-stu-id="88626-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="88626-126">America Online requiere que el certificado del servidor perimetral asignado al servicio perimetral de acceso tenga un uso mejorado de clave (EKU) de cliente.</span><span class="sxs-lookup"><span data-stu-id="88626-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="88626-127">En esta sección</span><span class="sxs-lookup"><span data-stu-id="88626-127">In This Section</span></span>

  - [<span data-ttu-id="88626-128">Resumen del certificado: conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88626-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="88626-129">Resumen de puertos: conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88626-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="88626-130">[Resumen de DNS: conectividad de mensajería instantánea pública en Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="88626-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

