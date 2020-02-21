---
title: 'Lync Server 2013: configuración de la recogida de llamadas de grupo'
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
ms.openlocfilehash: ef62fc903e70c0ff60cd86d124fbd092d9b394c1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="09f81-102">Configuración de la recogida de llamadas de grupo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09f81-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09f81-103">_**Última modificación del tema:** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="09f81-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="09f81-104">La actualización acumulativa para Lync Server 2013: febrero de 2013 presenta la llamada de grupo como una nueva característica de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="09f81-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="09f81-105">La recopilación de llamadas de grupo permite a los usuarios seleccionar llamadas que se llamen a otro usuario marcando un número de grupo de atención de llamadas.</span><span class="sxs-lookup"><span data-stu-id="09f81-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="09f81-106">Los componentes que los usos de la llamada de agrupación de grupos se instalan y habilitan automáticamente en el servidor front-end o el servidor Standard Edition al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="09f81-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="09f81-107">Sin embargo, debe configurar la recogida de llamadas de grupo para que esté disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="09f81-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="09f81-108">Esta sección le guiará a través de la configuración de la recogida de llamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="09f81-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="09f81-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="09f81-109">In This Section</span></span>

[<span data-ttu-id="09f81-110">Requisitos previos de configuración de llamada de grupo y derechos de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09f81-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="09f81-111">Proceso de implementación para la recogida de llamadas grupales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09f81-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="09f81-112">Implementar la herramienta SEFAUtil en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09f81-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="09f81-113">Configurar números de grupo de atención de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09f81-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="09f81-114">Habilitar la atención de llamadas grupales para los usuarios en Lync Server 2013 y asignar un número de grupo</span><span class="sxs-lookup"><span data-stu-id="09f81-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="09f81-115">Comunicar las asignaciones de atención de llamadas grupales a los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09f81-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="09f81-116">Opcional Comprobar la implementación de la llamada de grupo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09f81-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

