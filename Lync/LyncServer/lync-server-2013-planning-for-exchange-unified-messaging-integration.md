---
title: 'Lync Server 2013: Planeación de la integración de la mensajería unificada de Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Exchange Unified Messaging integration
ms:assetid: e7c63a71-2d99-4aa9-b649-36c1a431bdf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399031(v=OCS.15)
ms:contentKeyID: 48185880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e5e9c4e4e4a1e77f3ca7badc0a4549cb04cee94
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="24fe2-102">Planeación de la integración de la mensajería unificada de Exchange en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24fe2-102">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24fe2-103">_**Última modificación del tema:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="24fe2-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="24fe2-104">Lync Server 2013 admite la integración con la mensajería unificada (UM) de Exchange para combinar la mensajería de voz y la mensajería de correo electrónico en una única infraestructura de mensajería.</span><span class="sxs-lookup"><span data-stu-id="24fe2-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="24fe2-105">En Microsoft Exchange Server 2007 Service Pack 1 (SP1) y Microsoft Exchange Server 2010, la mensajería unificada de Exchange (UM) es una de las diversas funciones de Exchange Server que puede instalar y configurar.</span><span class="sxs-lookup"><span data-stu-id="24fe2-105">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="24fe2-106">En Microsoft Exchange Server 2013, la mensajería unificada de Exchange se ejecuta como un servicio en un servidor de buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="24fe2-106">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="24fe2-107">Para las implementaciones de Lync Server 2013 Enterprise Voice, la mensajería unificada combina la mensajería de voz y la mensajería de correo electrónico en un solo almacén que está disponible desde un teléfono (Outlook Voice Access) o un equipo.</span><span class="sxs-lookup"><span data-stu-id="24fe2-107">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="24fe2-108">La mensajería unificada y Lync Server 2013 funcionan de forma conjunta para proporcionar servicios de contestador automático, Outlook Voice Access y operador automático a los usuarios de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="24fe2-108">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="24fe2-109">Para obtener más información acerca de los cambios en la arquitectura de Microsoft Exchange Server 2013, consulte "Voice Architecture Changes" en la documentación [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730)de Microsoft exchange Server 2013 en.</span><span class="sxs-lookup"><span data-stu-id="24fe2-109">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="24fe2-110">Para que estas características se admitan en una implementación local de mensajería unificada de Exchange, debe estar ejecutando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="24fe2-110">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="24fe2-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) o el último Service Pack</span><span class="sxs-lookup"><span data-stu-id="24fe2-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="24fe2-112">Microsoft Exchange Server 2010 o Service Pack más reciente</span><span class="sxs-lookup"><span data-stu-id="24fe2-112">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="24fe2-113">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="24fe2-113">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="24fe2-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="24fe2-114">In This Section</span></span>

  - [<span data-ttu-id="24fe2-115">Características de la mensajería unificada integrada y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24fe2-115">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="24fe2-116">Componentes y topologías para mensajería unificada local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24fe2-116">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="24fe2-117">Directrices para la integración de la mensajería unificada local y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24fe2-117">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="24fe2-118">Proceso de implementación para la integración de la mensajería unificada local y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24fe2-118">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

