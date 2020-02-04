---
title: 'Lync Server 2013: Definir las reglas de normalización'
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
ms.openlocfilehash: b75883d99d218d711e9d96de7ebfd7d360972a6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="c51df-102">Definir las reglas de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c51df-102">Defining normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c51df-103">_**Última modificación del tema:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="c51df-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="c51df-104">Reglas de normalización de Lync Server 2013 usar expresiones regulares de .NET Framework para traducir números de teléfono marcados al formato E. 164; en otras palabras, las reglas de normalización toman el número de teléfono marcado por un usuario y convierten ese número al formato usado internamente por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c51df-104">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="c51df-105">Cada plan de marcado debe tener asignadas una o más reglas de normalización.</span><span class="sxs-lookup"><span data-stu-id="c51df-105">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="c51df-106">Para obtener más información sobre las reglas de normalización, consulte [planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="c51df-106">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="c51df-107">Para obtener más información sobre cómo escribir expresiones regulares, vea "expresiones regulares de .NET Framework [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)" en.</span><span class="sxs-lookup"><span data-stu-id="c51df-107">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="c51df-108">Puede usar cualquiera de los siguientes métodos para definir o editar una regla de normalización:</span><span class="sxs-lookup"><span data-stu-id="c51df-108">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="c51df-109">Use la herramienta **crear una regla de normalización** para especificar valores para los dígitos iniciales, la longitud, los dígitos que se van a quitar y los dígitos que se van a agregar y, a continuación, deje que el panel de control de Lync Server genere el patrón correspondiente y la regla de traducción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c51df-109">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="c51df-110">Escriba de forma manual expresiones regulares para definir el patrón de coincidencia y la regla de traducción.</span><span class="sxs-lookup"><span data-stu-id="c51df-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c51df-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c51df-111">In This Section</span></span>

  - [<span data-ttu-id="c51df-112">Crear o modificar una regla de normalización mediante la creación de una regla de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c51df-112">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="c51df-113">Crear o modificar una regla de normalización manualmente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c51df-113">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c51df-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c51df-114">See Also</span></span>


[<span data-ttu-id="c51df-115">Crear un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c51df-115">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="c51df-116">Modificar un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c51df-116">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

