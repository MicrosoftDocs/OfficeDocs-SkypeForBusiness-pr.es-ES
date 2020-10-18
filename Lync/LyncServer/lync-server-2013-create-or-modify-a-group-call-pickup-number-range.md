---
title: 'Lync Server 2013: crear o modificar un intervalo de números de llamada de llamada de grupo'
description: 'Lync Server 2013: crear o modificar un intervalo de números de atención de llamadas grupales.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc2072a5d80e9c3b09e0c0d2275233214a21e764
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577926"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="6b6d5-103">Crear o modificar un intervalo de números de atención de llamadas grupales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b6d5-103">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b6d5-104">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="6b6d5-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="6b6d5-105">Use el siguiente procedimiento para crear o modificar un intervalo de números del grupo de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-105">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6b6d5-106">Debe usar el shell de administración de Lync Server para crear, modificar, quitar y ver intervalos de números de llamada de llamadas de grupo en la tabla de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-106">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="6b6d5-107">Los intervalos de números de llamada de grupo no están disponibles en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-107">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6b6d5-108">El intervalo de números del grupo de atención a llamadas debe asignarse a un tipo de GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-108">The call pickup group number range must be assigned a type of GroupPickup.</span></span> <span data-ttu-id="6b6d5-109">Los usuarios solo están habilitados para la recogida de llamadas de grupo si el número de grupo al que se asignan es de tipo GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-109">Users are enabled for Group Call Pickup only if the group number that they are assigned is type GroupPickup.</span></span>



</div>

<span data-ttu-id="6b6d5-110">Los intervalos de números del grupo de recogida de llamadas deben cumplir con las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="6b6d5-110">The call pickup group number ranges must comply with the following rules:</span></span>

  - <span data-ttu-id="6b6d5-111">El número inicial del intervalo debe ser menor o igual al número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="6b6d5-112">El valor del número inicial del intervalo debe tener la misma longitud que el número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="6b6d5-p103">El intervalo numérico debe ser único. Este intervalo no se puede superponer con ningún otro.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="6b6d5-115">Si el intervalo de números comienza por el carácter \* o \# , el intervalo debe ser mayor que 100.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-115">If the number range begins with the character \* or \#, the range must be greater than 100.</span></span>

  - <span data-ttu-id="6b6d5-116">Valores válidos: deben coincidir con la cadena de expresión regular ( \[ \\ \* | \# \] ? \[ 1-9 \] \\ d {0,7} ) | ( \[ 1-9 \] \\ d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="6b6d5-116">Valid values: Must match the regular expression string (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}).</span></span> <span data-ttu-id="6b6d5-117">Esto significa que el valor debe ser una cadena que comience por el carácter \* o \# o un número del 1 al 9 (el primer carácter no puede ser un cero).</span><span class="sxs-lookup"><span data-stu-id="6b6d5-117">This means the value must be a string beginning with either the character \* or \# or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="6b6d5-118">Si el primer carácter es \* o \# , el siguiente carácter debe ser un número del 1 al 9 (no puede ser un cero).</span><span class="sxs-lookup"><span data-stu-id="6b6d5-118">If the first character is \* or \#, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="6b6d5-119">Los siguientes caracteres pueden ser cualquier número del 0 al 9, hasta un máximo de siete caracteres adicionales (por ejemplo, " \# 6000", " \* 92000", " \* 95551212" y "915551212").</span><span class="sxs-lookup"><span data-stu-id="6b6d5-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "\#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="6b6d5-120">Si el primer carácter no es \* o \# , el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido de hasta ocho caracteres, cada uno de los números del 0 al 9 (por ejemplo, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="6b6d5-120">If the first character is not \* or \#, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="6b6d5-121">Para crear o modificar un intervalo de grupo de recogida de llamadas</span><span class="sxs-lookup"><span data-stu-id="6b6d5-121">To create or modify a call pickup group range</span></span>

1.  <span data-ttu-id="6b6d5-122">Inicie sesión en el equipo donde esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6b6d5-122">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="6b6d5-123">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6b6d5-124">Use **New-CsCallParkOrbit** para crear un nuevo intervalo de números de grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-124">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="6b6d5-125">Use **set-CsCallParkOrbit** para modificar un intervalo existente de números de atención de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-125">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="6b6d5-126">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6b6d5-126">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    <span data-ttu-id="6b6d5-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6b6d5-127">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    <span data-ttu-id="6b6d5-128">En el ejemplo siguiente se muestra cómo cambiar un intervalo de números de las órbitas de estacionamiento de llamadas a grupos de RECALL.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-128">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6b6d5-129">Use este cmdlet para cambiar el tipo asignado a los intervalos de números solo si especificó inicialmente el tipo incorrecto y el intervalo de grupo todavía no está en uso.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-129">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="6b6d5-130">Si cambia el intervalo de números de CallPark a GroupPickup o viceversa y el intervalo de números ya está en uso, ya no podrá trabajar para ese intervalo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-130">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="6b6d5-131">Por ejemplo, si cambia un intervalo de números de CallPark a GroupPick, la aplicación estacionamiento de llamadas ya no podrá usar ese intervalo de órbitas para estacionar llamadas.</span><span class="sxs-lookup"><span data-stu-id="6b6d5-131">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6b6d5-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b6d5-132">See Also</span></span>


[<span data-ttu-id="6b6d5-133">Eliminar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b6d5-133">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="6b6d5-134">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="6b6d5-134">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="6b6d5-135">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="6b6d5-135">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

