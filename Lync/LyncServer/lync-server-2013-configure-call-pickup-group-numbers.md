---
title: 'Lync Server 2013: configurar los números del grupo de recogida de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call pickup group numbers
ms:assetid: 5cc67f0b-d70d-446a-8db1-befda8671121
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945631(v=OCS.15)
ms:contentKeyID: 51541479
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc2badf254fc42e9e8db401065467a6c673660ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-pickup-group-numbers-in-lync-server-2013"></a><span data-ttu-id="005e6-102">Configurar números de grupo de recogida de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="005e6-102">Configure call pickup group numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="005e6-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="005e6-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="005e6-104">La recogida de llamadas grupales se basa en la aplicación de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="005e6-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="005e6-105">Al implementar la recogida de llamadas grupales, debe configurar la tabla de llamadas en órbita con los rangos de números de teléfono que se designan como números de grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="005e6-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="005e6-106">Estos números de grupo son los números que los usuarios marcan para atender las llamadas que están sonando para otro usuario.</span><span class="sxs-lookup"><span data-stu-id="005e6-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="005e6-107">Al igual que sucede con los números de órbita de estacionamiento de llamadas, los números de grupo de atención a llamadas deben ser extensiones virtuales que no tengan asignado ningún usuario o teléfono.</span><span class="sxs-lookup"><span data-stu-id="005e6-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="005e6-108">Cada grupo de servidores front-end en el que se implementa la recogida de llamadas grupales puede tener uno o más intervalos de números de grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="005e6-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="005e6-109">Los intervalos de números de grupo deben ser únicos globalmente en la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="005e6-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="005e6-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="005e6-110">In This Section</span></span>

[<span data-ttu-id="005e6-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="005e6-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

