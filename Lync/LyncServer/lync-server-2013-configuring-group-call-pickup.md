---
title: 'Lync Server 2013: configuración de la recogida de llamadas grupales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Group Call Pickup
ms:assetid: b4b0a9a0-91c6-43a5-9e2b-a086caeb3f94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945645(v=OCS.15)
ms:contentKeyID: 51541505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3096c468b478da365bcfa0e38fa287a5c2ab57a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="e3746-102">Configuración de la recogida de llamadas grupales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3746-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3746-103">_**Última modificación del tema:** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="e3746-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="e3746-104">Actualización acumulativa para Lync Server 2013: febrero de 2013 presenta la recogida de llamadas grupales como una nueva característica de voz empresarial.</span><span class="sxs-lookup"><span data-stu-id="e3746-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="e3746-105">La recopilación de la llamada grupal permite que los usuarios recojan llamadas que están sonando por otro usuario marcando un número de grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e3746-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="e3746-106">Los componentes que usa la recogida de llamadas grupales se instalan y se habilitan automáticamente en el servidor front-end o el servidor Standard Edition al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="e3746-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e3746-107">Sin embargo, debe configurar la recogida de llamadas de grupo antes de que esté disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e3746-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="e3746-108">Esta sección le guiará a través de la configuración de la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="e3746-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e3746-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e3746-109">In This Section</span></span>

[<span data-ttu-id="e3746-110">Requisitos previos y derechos de usuario para la configuración de la llamada grupal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3746-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="e3746-111">Proceso de implementación para la recogida de llamadas grupales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3746-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="e3746-112">Deploy the SEFAUtil tool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3746-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="e3746-113">Configurar números de grupo de recogida de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3746-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="e3746-114">Habilitar la recogida de llamadas grupales para los usuarios en Lync Server 2013 y asignar un número de grupo</span><span class="sxs-lookup"><span data-stu-id="e3746-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="e3746-115">Comunicar las tareas de recogida de llamadas grupales a los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3746-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="e3746-116">Faculta Comprobar la implementación de la llamada grupal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3746-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

