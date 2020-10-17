---
title: 'Lync Server 2013: componentes y topologías para mensajería unificada local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da7b4c62daf2ed5bdc7416a704e2c70f18802419
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502517"
---
# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a><span data-ttu-id="b037e-102">Componentes y topologías para mensajería unificada local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b037e-102">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b037e-103">_**Última modificación del tema:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="b037e-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="b037e-104">En este tema se describen los componentes de Microsoft Exchange Server 2013 necesarios para proporcionar características de mensajería unificada (MU) de Exchange a la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b037e-104">This topic describes the Microsoft Exchange Server 2013 components required to provide Exchange Unified Messaging (UM) features to Lync Server 2013 deployment.</span></span> <span data-ttu-id="b037e-105">También se describen las topologías admitidas para la integración local de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b037e-105">It also describes the supported topologies for on-premises Exchange UM integration.</span></span>

<div>

## <a name="exchange-server-components"></a><span data-ttu-id="b037e-106">Componentes de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="b037e-106">Exchange Server Components</span></span>

<span data-ttu-id="b037e-107">Para proporcionar las características y los servicios de mensajería unificada de Exchange descritos en [características de mensajería unificada integrada y Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) a los usuarios de Enterprise Voice de su organización, debe implementar un servidor de buzones de correo y un servidor de acceso de cliente de Microsoft Exchange, que hospeda los buzones de usuario y proporciona una única ubicación de almacenamiento para el correo electrónico y el correo de voz</span><span class="sxs-lookup"><span data-stu-id="b037e-107">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="b037e-108">La mensajería unificada de Exchange se ejecuta como un servicio en los servidores de buzones y de acceso de cliente de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b037e-108">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="b037e-109">Para obtener más información acerca de los componentes de mensajería unificada de Exchange en Microsoft Exchange Server 2007 y Microsoft Exchange Server 2010, consulte [Deploying on-premises Exchange um to Provide Lync Server 2013 Voice Mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="b037e-109">For details about Exchange UM components in Microsoft Exchange Server 2007 and Microsoft Exchange Server 2010, see [Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="b037e-110">Topologías admitidas</span><span class="sxs-lookup"><span data-stu-id="b037e-110">Supported Topologies</span></span>

<span data-ttu-id="b037e-111">Puede implementar Lync Server 2013 y mensajería unificada de Exchange (UM) en el mismo bosque o en varios bosques.</span><span class="sxs-lookup"><span data-stu-id="b037e-111">You can deploy Lync Server 2013 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="b037e-112">Si la implementación abarca varios bosques, debe realizar los pasos de integración de Exchange para cada bosque de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b037e-112">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="b037e-113">Además, debe configurar cada bosque de Microsoft Exchange para que confíe en el bosque de Lync Server 2013 y en el bosque de Lync Server 2013 para confiar en cada bosque de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b037e-113">Furthermore, you must configure each Microsoft Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="b037e-114">Además de esta confianza de bosque, la configuración de mensajería unificada de Exchange para todos los usuarios debe establecerse en los objetos de usuario del bosque de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b037e-114">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Lync Server 2013 forest.</span></span>

<span data-ttu-id="b037e-115">Lync Server 2013 admite las siguientes topologías para la integración de mensajería unificada de Exchange:</span><span class="sxs-lookup"><span data-stu-id="b037e-115">Lync Server 2013 supports the following topologies for Exchange UM integration:</span></span>

  - <span data-ttu-id="b037e-116">Bosque único</span><span class="sxs-lookup"><span data-stu-id="b037e-116">Single forest</span></span>

  - <span data-ttu-id="b037e-117">Dominio único (es decir, un único bosque con un único dominio).</span><span class="sxs-lookup"><span data-stu-id="b037e-117">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="b037e-118">Lync Server 2013, Microsoft Exchange y todos los usuarios residen en el mismo dominio.</span><span class="sxs-lookup"><span data-stu-id="b037e-118">Lync Server 2013, Microsoft Exchange, and users all reside in the same domain.</span></span>

  - <span data-ttu-id="b037e-119">Varios dominios (es decir, un dominio raíz con uno o más dominios secundarios).</span><span class="sxs-lookup"><span data-stu-id="b037e-119">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="b037e-120">Lync Server 2013 y los servidores de Microsoft Exchange se implementan en dominios diferentes del dominio donde se crean los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b037e-120">Lync Server 2013, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="b037e-121">Los servidores de mensajería unificada de Exchange se pueden implementar en dominios diferentes del grupo de Lync Server 2013 que admiten.</span><span class="sxs-lookup"><span data-stu-id="b037e-121">Exchange UM servers can be deployed in different domains from the Lync Server 2013 pool they support.</span></span>

  - <span data-ttu-id="b037e-122">Varios bosques (es decir, un bosque de recursos).</span><span class="sxs-lookup"><span data-stu-id="b037e-122">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="b037e-123">Lync Server 2013 se implementa en un único bosque y, a continuación, los usuarios se distribuyen en varios bosques.</span><span class="sxs-lookup"><span data-stu-id="b037e-123">Lync Server 2013 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="b037e-124">Los atributos de mensajería unificada de Exchange de los usuarios deben replicarse en el bosque de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b037e-124">The users’ Exchange UM attributes must be replicated over to the Lync Server 2013 forest.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b037e-125">Exchange se puede implementar en varios bosques.</span><span class="sxs-lookup"><span data-stu-id="b037e-125">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="b037e-126">Cada organización de Exchange puede proporcionar la mensajería unificada de Exchange a sus usuarios o se puede implementar la mensajería unificada de Exchange en el mismo bosque que Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b037e-126">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Lync Server 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

