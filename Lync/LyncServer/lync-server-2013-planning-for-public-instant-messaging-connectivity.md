---
title: 'Lync Server 2013: Planeación de la conectividad de mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3b1ad49a24e1236dbea837c596beff5e9605902
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="aeb43-102">Planeación de la conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb43-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aeb43-103">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="aeb43-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="aeb43-104">La conectividad de mensajería instantánea pública es una clase de Federación y está configurada para permitir que los usuarios internos y externos de Lync Server 2013 puedan agregar contactos desde cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="aeb43-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="aeb43-105">Contactos de Messenger</span><span class="sxs-lookup"><span data-stu-id="aeb43-105">Messenger contacts</span></span>

  - <span data-ttu-id="aeb43-106">Toolbar\!</span><span class="sxs-lookup"><span data-stu-id="aeb43-106">Yahoo\!</span></span> <span data-ttu-id="aeb43-107">contacts</span><span class="sxs-lookup"><span data-stu-id="aeb43-107">contacts</span></span>

  - <span data-ttu-id="aeb43-108">Contactos de America Online (AOL)</span><span class="sxs-lookup"><span data-stu-id="aeb43-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="aeb43-109">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de la conectividad de mensajería instantánea pública de Microsoft Lync (PIC USL) ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="aeb43-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="aeb43-110">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="aeb43-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="aeb43-111">Messenger hasta la fecha de cierre del servicio.</span><span class="sxs-lookup"><span data-stu-id="aeb43-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="aeb43-112">Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="aeb43-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="aeb43-113">se ha anunciado.</span><span class="sxs-lookup"><span data-stu-id="aeb43-113">has been announced.</span></span> <span data-ttu-id="aeb43-114">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aeb43-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="aeb43-115">La capa de PIC es una licencia por usuario, por mes, que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="aeb43-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="aeb43-116">Service.</span><span class="sxs-lookup"><span data-stu-id="aeb43-116">Messenger.</span></span> <span data-ttu-id="aeb43-117">La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente que no se renovará.</span><span class="sxs-lookup"><span data-stu-id="aeb43-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="aeb43-118">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="aeb43-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="aeb43-119">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="aeb43-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="aeb43-120">La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas a través de mensajería instantánea y voz.</span><span class="sxs-lookup"><span data-stu-id="aeb43-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="aeb43-121">Esta clase de federación requiere las siguientes consideraciones de planificación:</span><span class="sxs-lookup"><span data-stu-id="aeb43-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="aeb43-122">Los usuarios de Windows Live Messenger pueden tener comunicación de audio/visual de punto a punto con los usuarios de Lync Server 2013, además de la mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="aeb43-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="aeb43-123">Los servidores perimetrales deben cumplir unos requisitos de puerto y protocolo específicos.</span><span class="sxs-lookup"><span data-stu-id="aeb43-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="aeb43-124">Para obtener más información, consulte [determinación de requisitos de firewall y de puerto a/V externos para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aeb43-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="aeb43-125">La mensajería instantánea de Yahoo no tiene requisitos únicos, excepto los que se usan normalmente en la planeación y la implementación del servidor perimetral típico que proporciona la Federación.</span><span class="sxs-lookup"><span data-stu-id="aeb43-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="aeb43-126">America Online requiere que el certificado del servidor perimetral asignado al servicio perimetral de acceso tenga un uso mejorado de clave (EKU) de cliente.</span><span class="sxs-lookup"><span data-stu-id="aeb43-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aeb43-127">En esta sección</span><span class="sxs-lookup"><span data-stu-id="aeb43-127">In This Section</span></span>

  - [<span data-ttu-id="aeb43-128">Resumen de certificado-conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb43-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="aeb43-129">Resumen de Puerto-conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb43-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="aeb43-130">[Resumen de DNS-conectividad de mensajería instantánea pública en Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aeb43-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

