---
title: 'Lync Server 2013: configurar extensiones de números de teléfono para las llamadas de estacionamiento'
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
ms.openlocfilehash: 6546488deb6ee1f00539944271f6f80cfc7a06b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="e5f69-102">Configurar extensiones de números de teléfono para las llamadas de estacionamiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5f69-102">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5f69-103">_**Última modificación del tema:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="e5f69-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="e5f69-104">La aplicación de estacionamiento de llamadas usa números de extensión en la tabla de órbitas de estacionamiento de llamadas para estacionar llamadas.</span><span class="sxs-lookup"><span data-stu-id="e5f69-104">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="e5f69-105">Debe configurar la tabla de órbitas de estacionamiento de llamadas con los intervalos de números de extensión que la organización reserva para las llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="e5f69-105">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="e5f69-106">Las extensiones deben ser virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado).</span><span class="sxs-lookup"><span data-stu-id="e5f69-106">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="e5f69-107">Cada grupo de Lync Server en el que se implementa y configura una aplicación de estacionamiento de llamadas puede tener uno o más intervalos de órbitas.</span><span class="sxs-lookup"><span data-stu-id="e5f69-107">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="e5f69-108">Los intervalos de órbitas deben ser únicos en todo el mundo en la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5f69-108">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e5f69-109">Debe activar la casilla de verificación <STRONG>Habilitar estacionamiento de llamadas</STRONG> en su Directiva de voz antes de poder usar el estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e5f69-109">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="e5f69-110">De forma predeterminada, esta opción no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e5f69-110">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e5f69-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e5f69-111">In This Section</span></span>

  - [<span data-ttu-id="e5f69-112">Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5f69-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="e5f69-113">Eliminar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5f69-113">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

