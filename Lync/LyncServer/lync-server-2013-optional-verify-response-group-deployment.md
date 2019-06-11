---
title: 'Lync Server 2013: (opcional) comprobar la implementación de grupos de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify Response Group deployment
ms:assetid: 202ca4ab-8e6d-44a4-b7c8-071133074feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687989(v=OCS.15)
ms:contentKeyID: 49733579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3b031ab8fdaac5249146faedafcc23517040b3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="fa5bb-102">Faculta Comprobar la implementación de grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa5bb-102">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa5bb-103">_**Última modificación del tema:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="fa5bb-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="fa5bb-104">Después de configurar el grupo de respuesta, debe comprobar la configuración para asegurarse de que los grupos de respuesta funcionan de la forma esperada.</span><span class="sxs-lookup"><span data-stu-id="fa5bb-104">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="fa5bb-105">Compruebe, como mínimo, los siguientes escenarios con los tipos de usuarios que se muestran a continuación:</span><span class="sxs-lookup"><span data-stu-id="fa5bb-105">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="fa5bb-106">**Usuarios**</span><span class="sxs-lookup"><span data-stu-id="fa5bb-106">**Users**</span></span>

  - <span data-ttu-id="fa5bb-107">Un usuario que está alojado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa5bb-107">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="fa5bb-108">Un usuario externo que usa la red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="fa5bb-108">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="fa5bb-109">Un agente que está alojado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa5bb-109">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="fa5bb-110">**Escenarios**</span><span class="sxs-lookup"><span data-stu-id="fa5bb-110">**Scenarios**</span></span>

  - <span data-ttu-id="fa5bb-111">El usuario de Lync Server 2013 llama al grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="fa5bb-111">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="fa5bb-112">El usuario externo llama al grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="fa5bb-112">The external user calls the response group.</span></span>

  - <span data-ttu-id="fa5bb-113">Un usuario llama al grupo de respuesta mientras el agente está ocupado con otra llamada y va a la cola.</span><span class="sxs-lookup"><span data-stu-id="fa5bb-113">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

