---
title: 'Lync Server 2013: Compatibilidad con la integración de mensajería unificada de Exchange hospedada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ba107c9a782acb15ccd8d57f82cf567f2b75e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="73706-102">Compatibilidad con la integración de mensajería unificada de Exchange hospedada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73706-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73706-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="73706-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="73706-104">La aplicación de enrutamiento ExUM de Lync Server 2013 admite la integración con mensajería unificada de Exchange (UM) en un entorno local, donde Lync Server 2013 y MU están instalados de forma local en su empresa, o en con la mu de Exchange hospedada por un proveedor de servicios, como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="73706-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="73706-105">![Implementación de mensajería unificada de Exchange de Lync Server local] (images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implementación de mensajería unificada de Exchange de Lync Server local")</span><span class="sxs-lookup"><span data-stu-id="73706-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="73706-106">Se admiten los siguientes modos:</span><span class="sxs-lookup"><span data-stu-id="73706-106">The following modes are supported:</span></span>

  - <span data-ttu-id="73706-107">**El modo**   local de Lync Server 2013 y la mensajería unificada de Exchange se implementan en servidores locales de su empresa.</span><span class="sxs-lookup"><span data-stu-id="73706-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="73706-108">**Modo entre locales**   Lync Server 2013 se implementa en servidores locales de su empresa y la mensajería unificada de Exchange se hospeda en una instalación de un proveedor de servicios en línea, como un centro de datos de Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="73706-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="73706-109">**Modo mixto su**   implementación de Lync Server 2013 tiene algunos buzones de usuario alojados en servidores locales que ejecutan Microsoft Exchange Server dentro de su empresa y algunos buzones alojados en un centro de datos de servicio de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="73706-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73706-110">El modo mixto se puede usar como solución transitoria durante la evaluación y stepwise la migración de los usuarios a la mensajería unificada de Exchange hospedada o como una solución permanente si opta por mantener locales los servicios de mensajería unificada de Exchange de los usuarios después de migrar otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="73706-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="73706-111">Para integrar Lync Server 2013 con mensajería unificada de Exchange hospedada, debe configurar un *espacio de direcciones SIP compartido* (también denominado *dominio dividido*).</span><span class="sxs-lookup"><span data-stu-id="73706-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="73706-112">En esta configuración, tanto Lync Server 2013 como el proveedor de servicios de mensajería unificada de Exchange hospedado por terceros pueden acceder al mismo espacio de direcciones de dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="73706-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="73706-113">Para obtener más información, consulte [arquitectura de integración de mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="73706-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

