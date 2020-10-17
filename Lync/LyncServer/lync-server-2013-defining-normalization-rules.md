---
title: 'Lync Server 2013: definir reglas de normalización'
description: 'Lync Server 2013: definir reglas de normalización.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a123e17b1d3256781ff34e4cade2b344ba8fe14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542046"
---
# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="94bb9-103">Definición de reglas de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94bb9-103">Defining normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94bb9-104">_**Última modificación del tema:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="94bb9-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="94bb9-105">Las reglas de normalización de Lync Server 2013 utilizan expresiones regulares de .NET Framework para traducir números de teléfono marcados al formato E. 164; es decir, las reglas de normalización toman el número de teléfono marcado por un usuario y convierten ese número al formato usado internamente por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94bb9-105">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="94bb9-106">Cada plan de marcado debe tener asignadas una o más reglas de normalización.</span><span class="sxs-lookup"><span data-stu-id="94bb9-106">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="94bb9-107">Para obtener más información sobre las reglas de normalización, consulte [planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="94bb9-107">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="94bb9-108">Para obtener más información sobre cómo escribir expresiones regulares, consulte "expresiones regulares de .NET Framework" en [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="94bb9-108">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="94bb9-109">Puede usar cualquiera de los siguientes métodos para definir o editar una regla de normalización:</span><span class="sxs-lookup"><span data-stu-id="94bb9-109">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="94bb9-110">Use la herramienta **generar una regla de normalización** para especificar valores para los dígitos iniciales, la longitud, los dígitos que se van a quitar y los dígitos que se van a agregar y, a continuación, dejar que el panel de control de Lync Server genere el patrón de coincidencia y la regla de conversión correspondientes.</span><span class="sxs-lookup"><span data-stu-id="94bb9-110">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="94bb9-111">Escriba expresiones regulares manualmente para definir el patrón de comparación y la regla de traslación.</span><span class="sxs-lookup"><span data-stu-id="94bb9-111">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="94bb9-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="94bb9-112">In This Section</span></span>

  - [<span data-ttu-id="94bb9-113">Crear o modificar una regla de normalización con la creación de una regla de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94bb9-113">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="94bb9-114">Crear o modificar una regla de normalización manualmente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94bb9-114">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="94bb9-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94bb9-115">See Also</span></span>


[<span data-ttu-id="94bb9-116">Crear un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94bb9-116">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="94bb9-117">Modificar un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94bb9-117">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

