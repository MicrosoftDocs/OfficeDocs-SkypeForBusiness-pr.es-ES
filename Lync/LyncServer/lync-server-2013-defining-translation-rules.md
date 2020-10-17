---
title: 'Lync Server 2013: definición de reglas de conversión'
description: 'Lync Server 2013: definición de reglas de conversión.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining translation rules
ms:assetid: 4f6b975a-77e6-474c-9171-b139d84138c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398322(v=OCS.15)
ms:contentKeyID: 48184093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0c59225c8dc74d7d97bf3536c7b7073bc977925
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568396"
---
# <a name="defining-translation-rules-in-lync-server-2013"></a><span data-ttu-id="a41d1-103">Definición de reglas de conversión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a41d1-103">Defining translation rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a41d1-104">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a41d1-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a41d1-105">Lync Server 2013 Enterprise Voice enruta las llamadas en función de los números de teléfono normalizados al formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="a41d1-105">Lync Server 2013 Enterprise Voice routes calls based on phone numbers normalized to E.164 format.</span></span> <span data-ttu-id="a41d1-106">Esto significa que todas las cadenas marcadas deben normalizarse al formato E. 164 para realizar búsquedas inversas de números (RNL), de modo que se puedan traducir al URI del SIP correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a41d1-106">This means that all dialed strings must be normalized to E.164 format for the purpose of performing reverse number lookup (RNL) so they can be translated to their matching SIP URI.</span></span> <span data-ttu-id="a41d1-107">Lync Server 2013 proporciona la capacidad de manipular el identificador llamado y la presentación del identificador de llamada.</span><span class="sxs-lookup"><span data-stu-id="a41d1-107">Lync Server 2013 provides the ability to manipulate the called ID and the caller ID presentation.</span></span>

<span data-ttu-id="a41d1-108">En esta sección se explica cómo manipular el identificador llamado y el identificador del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a41d1-108">This section discusses how to manipulate the called ID and caller ID.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a41d1-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a41d1-109">In This Section</span></span>

  - [<span data-ttu-id="a41d1-110">Presentación del identificador de llamada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a41d1-110">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)

  - [<span data-ttu-id="a41d1-111">Presentación del identificador denominado presentación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a41d1-111">Called ID presentation in Lync Server 2013</span></span>](lync-server-2013-called-id-presentation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a41d1-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a41d1-112">See Also</span></span>


[<span data-ttu-id="a41d1-113">Definición de reglas de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a41d1-113">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

