---
title: Crear o modificar un intervalo de números de recogida de llamadas en grupo en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Cree o modifique un intervalo de números de recogida de llamadas de grupo en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: e71915519014b1fa4cfffa3172327e9949ed73a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100426"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="1a309-103">Crear o modificar un intervalo de números de recogida de llamadas en grupo en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="1a309-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="1a309-104">Cree o modifique un intervalo de números de recogida de llamadas de grupo en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="1a309-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="1a309-105">La recogida de llamadas en grupo se basa en la aplicación Estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1a309-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="1a309-106">Al implementar la recogida de llamadas de grupo, debe configurar la tabla de órbitas de estacionamiento de llamadas con intervalos de números de teléfono designados como números de grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1a309-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="1a309-107">Estos números de grupo son los números que los usuarios marcan para recoger las llamadas que están sonando para otro usuario.</span><span class="sxs-lookup"><span data-stu-id="1a309-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="1a309-108">Al igual que los números de órbita de estacionamiento de llamadas, los números de grupo de recogida de llamadas deben ser extensiones virtuales que no tienen ningún usuario o teléfono asignado.</span><span class="sxs-lookup"><span data-stu-id="1a309-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="1a309-109">Cada grupo de servidores front-end donde implemente la recogida de llamadas de grupo puede tener uno o más intervalos de números de grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1a309-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="1a309-110">Los intervalos de números de grupo deben ser únicos globalmente en la implementación y deben asignarse como el **tipo GroupPickup.**</span><span class="sxs-lookup"><span data-stu-id="1a309-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="1a309-111">Use el siguiente procedimiento para crear o modificar un intervalo de números de grupo de recogida de llamadas en la tabla de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1a309-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="1a309-112">Debe usar el Shell de administración de Skype Empresarial Server para crear, modificar, quitar y ver intervalos de números de recogida de llamadas de grupo en la tabla de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1a309-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="1a309-113">Los intervalos de números de recogida de llamadas de grupo no están disponibles en el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1a309-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="1a309-114">Los intervalos de números de grupo de recogida de llamadas deben cumplir las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="1a309-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="1a309-115">El número inicial del intervalo debe ser menor o igual al número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="1a309-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="1a309-116">El valor del número inicial del intervalo debe tener la misma longitud que el número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="1a309-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="1a309-p104">El intervalo numérico debe ser único. Este intervalo no se puede superponer con ningún otro.</span><span class="sxs-lookup"><span data-stu-id="1a309-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="1a309-119">Si el intervalo de números comienza con el carácter \* o #, el intervalo debe ser mayor que 100.</span><span class="sxs-lookup"><span data-stu-id="1a309-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="1a309-120">Valores válidos: debe coincidir con la cadena de expresión regular ([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="1a309-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="1a309-121">Esto significa que el valor debe ser una cadena que comienza con el carácter o # o un número \* del 1 al 9 (el primer carácter no puede ser cero).</span><span class="sxs-lookup"><span data-stu-id="1a309-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="1a309-122">Si el primer carácter es o #, el siguiente carácter debe ser un número del 1 al \* 9 (no puede ser cero).</span><span class="sxs-lookup"><span data-stu-id="1a309-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="1a309-123">Los caracteres posteriores pueden ser cualquier número de 0 a 9 hasta siete caracteres adicionales (por ejemplo, "#6000", " \* 92000", " \* 95551212" y "915551212").</span><span class="sxs-lookup"><span data-stu-id="1a309-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="1a309-124">Si el primer carácter no es o #, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido de hasta ocho caracteres, cada uno de \* 0 a 9 (por ejemplo, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="1a309-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="1a309-125">Para crear o modificar un intervalo de grupos de recogida de llamadas</span><span class="sxs-lookup"><span data-stu-id="1a309-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="1a309-126">Inicie sesión en el equipo donde skype empresarial Server Management Shell está instalado como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="1a309-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="1a309-127">Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="1a309-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="1a309-128">Use **New-CsCallParkOrbit para** crear un nuevo intervalo de números de grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1a309-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="1a309-129">Use **Set-CsCallParkOrbit para** modificar un intervalo existente de números de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1a309-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="1a309-130">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1a309-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="1a309-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1a309-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="1a309-132">En el ejemplo siguiente se muestra cómo cambiar un intervalo de números de órbitas de estacionamiento de llamadas a grupos de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1a309-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="1a309-133">Use este cmdlet para cambiar el tipo asignado a intervalos de números solo si inicialmente especificó el tipo incorrecto y el intervalo de grupos aún no está en uso.</span><span class="sxs-lookup"><span data-stu-id="1a309-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="1a309-134">Si cambia el intervalo de números de CallPark a GroupPickup o viceversa y el intervalo de números ya está en uso, el estacionamiento de llamadas o la recogida de llamadas de grupo dejarán de funcionar para ese intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="1a309-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="1a309-135">Por ejemplo, si cambia un intervalo de números de CallPark a GroupPick, la aplicación estacionamiento de llamadas ya no puede usar ese rango de órbitas para estacionar llamadas.</span><span class="sxs-lookup"><span data-stu-id="1a309-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a309-136">Ver también</span><span class="sxs-lookup"><span data-stu-id="1a309-136">See also</span></span>

[<span data-ttu-id="1a309-137">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="1a309-137">New-CsCallParkOrbit</span></span>](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="1a309-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="1a309-138">Set-CsCallParkOrbit</span></span>](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="1a309-139">Eliminar un intervalo de órbitas para estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="1a309-139">Delete a Call Park Orbit Range</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)