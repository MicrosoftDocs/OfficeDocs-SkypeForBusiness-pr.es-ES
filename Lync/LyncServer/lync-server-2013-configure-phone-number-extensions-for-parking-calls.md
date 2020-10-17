---
title: 'Lync Server 2013: configurar extensiones de números de teléfono para las llamadas de estacionamiento'
description: 'Lync Server 2013: configurar extensiones de números de teléfono para las llamadas de estacionamiento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6219e04243d0c19bc37251f7d113f7ebdd09fb72
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548836"
---
# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="f34f7-103">Configurar extensiones de números de teléfono para las llamadas de estacionamiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f34f7-103">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f34f7-104">_**Última modificación del tema:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="f34f7-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="f34f7-105">La aplicación de estacionamiento de llamadas usa números de extensión en la tabla de órbitas de estacionamiento de llamadas para estacionar llamadas.</span><span class="sxs-lookup"><span data-stu-id="f34f7-105">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="f34f7-106">Debe configurar la tabla de órbitas de estacionamiento de llamadas con los intervalos de números de extensión que la organización reserva para las llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="f34f7-106">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="f34f7-107">Las extensiones deben ser virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado).</span><span class="sxs-lookup"><span data-stu-id="f34f7-107">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="f34f7-108">Cada grupo de Lync Server en el que se implementa y configura una aplicación de estacionamiento de llamadas puede tener uno o más intervalos de órbitas.</span><span class="sxs-lookup"><span data-stu-id="f34f7-108">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="f34f7-109">Los intervalos de órbitas deben ser únicos en todo el mundo en la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f34f7-109">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f34f7-110">Debe activar la casilla de verificación <STRONG>Habilitar estacionamiento de llamadas</STRONG> en su Directiva de voz antes de poder usar el estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f34f7-110">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="f34f7-111">De forma predeterminada, esta opción no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f34f7-111">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f34f7-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f34f7-112">In This Section</span></span>

  - [<span data-ttu-id="f34f7-113">Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f34f7-113">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="f34f7-114">Eliminar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f34f7-114">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

