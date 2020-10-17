---
title: Lync Server 2013 compatibilidad con la integración de mensajería unificada de Exchange hospedada
description: Lync Server 2013 compatibilidad con la integración de mensajería unificada de Exchange hospedada.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88920667d703bc634921903e8e3995cb65db6873
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546326"
---
# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="62578-103">Compatibilidad con la integración de mensajería unificada de Exchange hospedada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62578-103">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62578-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="62578-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="62578-105">La aplicación Lync Server 2013 ExUM de enrutamiento admite la integración con la mensajería unificada de Exchange en un entorno local, donde Lync Server 2013 y la mensajería unificada de Exchange están instaladas localmente en la empresa o con la mensajería unificada de Exchange hospedada por un proveedor de servicios, tal como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="62578-105">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="62578-106">![Implementación local de mensajería unificada de Lync Server Exchange](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implementación local de mensajería unificada de Lync Server Exchange")</span><span class="sxs-lookup"><span data-stu-id="62578-106">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="62578-107">Se admiten los siguientes modos:</span><span class="sxs-lookup"><span data-stu-id="62578-107">The following modes are supported:</span></span>

  - <span data-ttu-id="62578-108">**Modo local**     Lync Server 2013 y la mensajería unificada de Exchange se implementan en servidores locales de la empresa.</span><span class="sxs-lookup"><span data-stu-id="62578-108">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="62578-109">**Modo**     entre locales Lync Server 2013 se implementa en servidores locales de la empresa y la mensajería unificada de Exchange se hospeda en las instalaciones de un proveedor de servicios en línea, como un centro de datos de Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="62578-109">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="62578-110">**Modo mixto**     La implementación de Lync Server 2013 tiene algunos buzones de usuario alojados en servidores locales que ejecutan Microsoft Exchange Server en su empresa y otros buzones en un centro de datos de servicio de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="62578-110">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="62578-111">El modo mixto se puede usar como solución transitoria durante la evaluación y la migración de paso a paso de usuarios a la mensajería unificada de Exchange hospedada o como una solución permanente si opta por mantener algunos servicios de mensajería unificada de Exchange de los usuarios de forma local después de migrar otros.</span><span class="sxs-lookup"><span data-stu-id="62578-111">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="62578-112">Para integrar Lync Server 2013 con mensajería unificada de Exchange hospedada, debe configurar un *espacio de direcciones SIP compartido* (también denominado *dominio dividido*).</span><span class="sxs-lookup"><span data-stu-id="62578-112">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="62578-113">En esta configuración, tanto Lync Server 2013 como el proveedor de servicios de mensajería unificada de Exchange hospedado por terceros pueden acceder al mismo espacio de direcciones de dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="62578-113">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="62578-114">Para obtener más información, consulte [arquitectura de integración de mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="62578-114">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

