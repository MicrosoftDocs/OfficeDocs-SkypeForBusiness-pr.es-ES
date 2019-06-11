---
title: 'Lync Server 2013: configurar extensiones de números de teléfono para llamadas de aparcamiento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0a0fd55b851715fe8aef238797392af6317dff0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="29c09-102">Configurar extensiones de números de teléfono para llamadas de aparcamiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29c09-102">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29c09-103">_**Última modificación del tema:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="29c09-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="29c09-104">La aplicación de estacionamiento de llamadas usa números de extensión en la tabla de llamadas de la órbita de estacionamiento para detener llamadas.</span><span class="sxs-lookup"><span data-stu-id="29c09-104">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="29c09-105">Debe configurar la tabla de llamadas en órbita con los intervalos de números de extensión en los que la organización reserva las llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="29c09-105">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="29c09-106">Estas extensiones tienen que ser extensiones virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado).</span><span class="sxs-lookup"><span data-stu-id="29c09-106">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="29c09-107">Cada grupo de Lync Server en el que se implementa y configura una aplicación de estacionamiento de llamadas puede tener uno o más intervalos Orbitantes.</span><span class="sxs-lookup"><span data-stu-id="29c09-107">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="29c09-108">Los intervalos de órbita deben ser únicos globalmente en la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29c09-108">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="29c09-109">Debe activar la casilla <STRONG>Habilitar estacionamiento de llamada</STRONG> en su Directiva de voz antes de poder usar el parque de llamadas.</span><span class="sxs-lookup"><span data-stu-id="29c09-109">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="29c09-110">De forma predeterminada, esta opción no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="29c09-110">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="29c09-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="29c09-111">In This Section</span></span>

  - [<span data-ttu-id="29c09-112">Crear o modificar un intervalo orbitar de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29c09-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="29c09-113">Eliminar un intervalo orbitar de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29c09-113">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

