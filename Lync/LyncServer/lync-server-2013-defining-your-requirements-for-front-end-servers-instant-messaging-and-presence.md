---
title: 'Lync Server 2013: definición de los requisitos para los servidores front-end, la mensajería instantánea y la presencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82cce58ab401149871073f6bc49ed4c53f301cb7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="08f6c-102">Definición de los requisitos para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08f6c-102">Defining your requirements for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08f6c-103">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="08f6c-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="08f6c-104">La tarea principal de la planeación de la mensajería instantánea (MI) y la presencia es comprobar que tenga suficientes servidores front-end para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="08f6c-104">The main task of planning for instant messaging (IM) and presence is ensuring that you have enough Front End Servers for your users.</span></span>

<div>

## <a name="enabling-communication-with-external-users"></a><span data-ttu-id="08f6c-105">Habilitación de la comunicación con usuarios externos</span><span class="sxs-lookup"><span data-stu-id="08f6c-105">Enabling Communication with External Users</span></span>

<span data-ttu-id="08f6c-106">Puede aumentar en gran medida los beneficios de su inversión en Lync Server al permitir que los usuarios se comuniquen con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="08f6c-106">You can greatly increase the benefits of your investment in Lync Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="08f6c-107">Entre los usuarios externos se pueden incluir:</span><span class="sxs-lookup"><span data-stu-id="08f6c-107">External users can include:</span></span>

  - <span data-ttu-id="08f6c-108">**Usuarios remotos**   los propios usuarios de su organización, cuando trabajan fuera de los firewalls y están usando sus equipos portátiles u otros dispositivos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="08f6c-108">**Remote users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server devices.</span></span>

  - <span data-ttu-id="08f6c-109">**Usuarios federados**   usuarios de empresas con las que trabaja y que también ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="08f6c-109">**Federated users**   Users from companies you work with who also run Lync Server.</span></span> <span data-ttu-id="08f6c-110">Para habilitar a sus usuarios para que se pongan en contacto fácilmente con estos usuarios, cree relaciones federadas con estas compañías.</span><span class="sxs-lookup"><span data-stu-id="08f6c-110">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="08f6c-111">**Usuarios públicos los**   usuarios de servicios de mensajería instantánea pública, como los servicios de mensajería instantánea proporcionados por la red de\!Windows Live de servicios de Internet, Yahoo y AOL, y los usuarios de proveedores y servidores que usan el protocolo extensible de mensajería y presencia (XMPP), como Google Talk.</span><span class="sxs-lookup"><span data-stu-id="08f6c-111">**Public users**   Users of public IM services, such as IM services provided by the Windows Live network of Internet services, Yahoo\!, and AOL, and users of providers and servers that use Extensible Messaging and Presence Protocol (XMPP), such as Google Talk.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08f6c-112">Tenga en cuenta que quizás sea necesaria otra licencia para la conectividad de mensajería instantánea pública con Windows Live, AOL y Yahoo!.</span><span class="sxs-lookup"><span data-stu-id="08f6c-112">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo!</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="08f6c-113">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="08f6c-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="08f6c-114">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="08f6c-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="08f6c-115">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="08f6c-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="08f6c-116">Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="08f6c-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="08f6c-117">se ha anunciado.</span><span class="sxs-lookup"><span data-stu-id="08f6c-117">has been announced.</span></span> <span data-ttu-id="08f6c-118">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="08f6c-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="08f6c-119">La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="08f6c-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="08f6c-120">Service.</span><span class="sxs-lookup"><span data-stu-id="08f6c-120">Messenger.</span></span> <span data-ttu-id="08f6c-121">La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</span><span class="sxs-lookup"><span data-stu-id="08f6c-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="08f6c-122">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="08f6c-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="08f6c-123">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="08f6c-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="08f6c-124">La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</span><span class="sxs-lookup"><span data-stu-id="08f6c-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="08f6c-125">Para habilitar uno o todos estos escenarios, debe implementar un servidor perimetral que ayude a habilitar las comunicaciones seguras entre la implementación de Lync Server y los usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="08f6c-125">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server deployment and external users.</span></span> <span data-ttu-id="08f6c-126">Los usuarios remotos de su organización y los usuarios de organizaciones federadas podrán ver la presencia de los demás y comunicarse mediante MI.</span><span class="sxs-lookup"><span data-stu-id="08f6c-126">Your organization’s remote users and users at federated organizations will be able to see each other’s presence and communicate using IM.</span></span> <span data-ttu-id="08f6c-127">Para obtener información detallada sobre cómo habilitar la comunicación con usuarios externos, consulte [Planning for external User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="08f6c-127">For details about enabling communication with external users, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-im-content"></a><span data-ttu-id="08f6c-128">Archivado del contenido de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="08f6c-128">Archiving IM Content</span></span>

<span data-ttu-id="08f6c-129">Lync Server proporciona características que se pueden usar si la organización debe seguir las normas de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="08f6c-129">Lync Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="08f6c-130">Puede usar el archivado para archivar el contenido de los mensajes de mensajería instantánea para todos los usuarios de la organización o solo para determinados usuarios que especifique.</span><span class="sxs-lookup"><span data-stu-id="08f6c-130">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="08f6c-131">Para obtener más información, consulte [planeación del archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="08f6c-131">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="08f6c-132">Si también tiene implementado Microsoft Exchange Server 2013, puede integrar el archivado de datos de Exchange con el archivado de datos de Lync Server y usar una única herramienta para buscar en ambos tipos de datos archivados.</span><span class="sxs-lookup"><span data-stu-id="08f6c-132">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Lync Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="08f6c-133">Para obtener más información, consulte [configuración de Microsoft Lync server 2013 para usar el archivado de Microsoft Exchange server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="08f6c-133">For more information, see [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

