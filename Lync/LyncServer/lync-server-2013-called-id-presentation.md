---
title: 'Lync Server 2013: presentación del identificador denominado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bd84e60118697c94aba6c6088de68fc37d34c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="5764a-102">Llamada presentación de identificación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5764a-102">Called ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5764a-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5764a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5764a-104">Con Lync Server 2010, el número de teléfono de la persona que se llama (es decir, el número de teléfono llamado) se puede traducir desde el formato E. 164 al formato de marcado local requerido por el interlocutor troncal (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el tronco del SIP).</span><span class="sxs-lookup"><span data-stu-id="5764a-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="5764a-105">Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="5764a-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5764a-106">La capacidad de asociar una o más reglas de traducción con una configuración de telefonía IP empresarial está pensada para su uso como <EM>alternativa</EM> a la configuración de reglas de traducción en el punto de conexión del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="5764a-106">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="5764a-107">No asociar reglas de traducción con una configuración de telefonía IP empresarial si ha configurado reglas de traducción en el punto de conexión del mismo nivel porque las dos reglas podrían entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="5764a-107">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="5764a-108">Puede usar cualquiera de los siguientes métodos para crear o modificar una regla de traducción:</span><span class="sxs-lookup"><span data-stu-id="5764a-108">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="5764a-109">Use la herramienta **generar una regla de traducción** para especificar valores para los dígitos de inicio, la longitud, los dígitos que se van a quitar y los dígitos que se van a agregar y, a continuación, permita que el panel de control de Lync Server genere el patrón correspondiente y la regla de traducción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5764a-109">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="5764a-110">Escriba de forma manual expresiones regulares para definir el patrón de coincidencia y la regla de traducción.</span><span class="sxs-lookup"><span data-stu-id="5764a-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5764a-111">Para obtener información sobre cómo escribir expresiones regulares, vea "expresiones regulares de .NET Framework" <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>en.</span><span class="sxs-lookup"><span data-stu-id="5764a-111">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5764a-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5764a-112">In This Section</span></span>

  - [<span data-ttu-id="5764a-113">Crear o modificar una regla de traducción con la herramienta generar una regla de traducción de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5764a-113">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="5764a-114">Crear o modificar una regla de traducción de forma manual en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5764a-114">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5764a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5764a-115">See Also</span></span>


[<span data-ttu-id="5764a-116">Presentación de la identificación de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5764a-116">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

