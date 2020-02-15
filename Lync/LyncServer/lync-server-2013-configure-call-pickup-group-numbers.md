---
title: 'Lync Server 2013: configurar números de grupo de recogida de llamadas'
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
ms.openlocfilehash: 42023f82240e99695678bc25f1f38b7a20234d37
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-pickup-group-numbers-in-lync-server-2013"></a><span data-ttu-id="47341-102">Configurar números de grupo de atención de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47341-102">Configure call pickup group numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47341-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="47341-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="47341-104">La recogida de llamadas de grupo se basa en la aplicación de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="47341-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="47341-105">Al implementar la atención de llamadas grupales, puede configurar la tabla de órbitas de estacionamiento de llamadas con los intervalos de números de teléfono que se designan como números de grupo de atención de llamadas.</span><span class="sxs-lookup"><span data-stu-id="47341-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="47341-106">Estos números de grupo son los números que los usuarios marcan para atender las llamadas que están sonando para otro usuario.</span><span class="sxs-lookup"><span data-stu-id="47341-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="47341-107">Al igual que los números de órbitas de estacionamiento de llamadas, los números de grupo de atención de llamadas deben ser extensiones virtuales que no tengan asignado ningún usuario ni teléfono.</span><span class="sxs-lookup"><span data-stu-id="47341-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="47341-108">Cada grupo de servidores front-end en el que se implementa la recogida de llamadas grupales puede tener uno o más intervalos de números de grupo de atención de llamadas.</span><span class="sxs-lookup"><span data-stu-id="47341-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="47341-109">Los intervalos de números de grupo deben ser únicos en todo el mundo en la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="47341-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="47341-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="47341-110">In This Section</span></span>

[<span data-ttu-id="47341-111">Crear o modificar un intervalo de números de atención de llamadas grupales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47341-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

