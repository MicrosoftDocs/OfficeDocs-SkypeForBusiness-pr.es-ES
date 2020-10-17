---
title: 'Lync Server 2013: presentación del identificador denominado'
description: 'Lync Server 2013: presentación del identificador denominado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b438c7c19bc3c4ad641a8b9f8dac319c9fc2b1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565206"
---
# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="b533c-103">Presentación del identificador denominado presentación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b533c-103">Called ID presentation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b533c-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b533c-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b533c-105">Con Lync Server 2010, el número de teléfono de la persona que ha llamado (es decir, el número de teléfono llamado) se puede traducir del formato E. 164 al formato de marcado local necesario para el tronco del mismo nivel (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el tronco SIP).</span><span class="sxs-lookup"><span data-stu-id="b533c-105">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="b533c-106">Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="b533c-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b533c-p102">La capacidad de asociar una o más reglas de conversión con una configuración de tronco de Enterprise Voice sirve de <EM>alternativa</EM> para configurar reglas de conversión en la entidad del mismo nivel que el tronco. No asocie reglas de conversión a una configuración de tronco de Enterprise Voice si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="b533c-p102">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer. Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="b533c-109">Puede usar cualquiera de los métodos siguientes para crear o modificar una regla de conversión:</span><span class="sxs-lookup"><span data-stu-id="b533c-109">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="b533c-110">Use la herramienta **generar una regla de conversión** para especificar valores para los dígitos iniciales, la longitud, los dígitos que se van a quitar y los dígitos que se van a agregar y, a continuación, dejar que el panel de control de Lync Server genere el patrón de coincidencia y la regla de conversión correspondientes.</span><span class="sxs-lookup"><span data-stu-id="b533c-110">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="b533c-111">Escriba expresiones regulares manualmente para definir el patrón de comparación y la regla de traslación.</span><span class="sxs-lookup"><span data-stu-id="b533c-111">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b533c-112">Para obtener información sobre cómo escribir expresiones regulares, consulte "expresiones regulares de .NET Framework" en <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A> .</span><span class="sxs-lookup"><span data-stu-id="b533c-112">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b533c-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b533c-113">In This Section</span></span>

  - [<span data-ttu-id="b533c-114">Crear o modificar una regla de conversión mediante la herramienta generar una regla de conversión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b533c-114">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="b533c-115">Crear o modificar una regla de conversión de forma manual en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b533c-115">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b533c-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b533c-116">See Also</span></span>


[<span data-ttu-id="b533c-117">Presentación del identificador de llamada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b533c-117">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

