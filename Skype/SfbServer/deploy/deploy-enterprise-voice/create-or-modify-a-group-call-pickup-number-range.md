---
title: Crear o modificar un intervalo numérico de respuesta de llamadas grupales en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- IT_Skype16
ms.custom:
- Strat_SB_Admin
- Strat_SB_Admin
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Crear o modificar un rango de números de grupo llamar recogida en Skype para Business Server Telefonía IP empresarial.
ms.openlocfilehash: 3a717f5607764ef1d5677e7bc70368f8803fc854
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business-2015"></a><span data-ttu-id="2f929-103">Crear o modificar un intervalo numérico de respuesta de llamadas grupales en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="2f929-103">Create or modify a Group Call Pickup number range in Skype for Business 2015</span></span>
 
<span data-ttu-id="2f929-104">Crear o modificar un rango de números de grupo llamar recogida en Skype para Business Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="2f929-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="2f929-105">Grupo llame recogida se basa en la aplicación de llamada Park.</span><span class="sxs-lookup"><span data-stu-id="2f929-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="2f929-106">Al implementar grupo llamar recogida, debe configurar la tabla de órbita de parque de llamada con los rangos de números de teléfono que se designan como llamar a números de grupo de recogida.</span><span class="sxs-lookup"><span data-stu-id="2f929-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="2f929-107">Estos números de grupo son los números que los usuarios marcan para atender las llamadas que están sonando para otro usuario.</span><span class="sxs-lookup"><span data-stu-id="2f929-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>
  
<span data-ttu-id="2f929-108">Al igual que sucede con los números de órbita de estacionamiento de llamadas, los números de grupo de atención a llamadas deben ser extensiones virtuales que no tengan asignado ningún usuario o teléfono.</span><span class="sxs-lookup"><span data-stu-id="2f929-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="2f929-109">Cada grupo de servidores Front-End donde implementar grupo llamar recogida puede tener uno o más rangos de números de grupo recogida de llamada.</span><span class="sxs-lookup"><span data-stu-id="2f929-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="2f929-110">Estos intervalos tienen que ser únicos en toda la implementación y deben asignarse como el tipo **GroupPickup**.</span><span class="sxs-lookup"><span data-stu-id="2f929-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>
  
<span data-ttu-id="2f929-111">Use el siguiente procedimiento para crear o modificar un intervalo de números del grupo de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="2f929-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2f929-112">Debe utilizar Skype para negocios de Shell de administración de servidor para crear, modificar, eliminar y ver intervalos numéricos de grupo llamar recogida en la tabla de órbita llamada park.</span><span class="sxs-lookup"><span data-stu-id="2f929-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="2f929-113">Intervalos numéricos de llamar a la recogida de grupo no están disponibles en Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="2f929-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="2f929-114">Los intervalos de números del grupo de atención de llamadas deben cumplir con las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="2f929-114">The call pickup group number ranges must comply with the following rules:</span></span>
  
- <span data-ttu-id="2f929-115">El número inicial del intervalo debe ser menor o igual al número final.</span><span class="sxs-lookup"><span data-stu-id="2f929-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
- <span data-ttu-id="2f929-116">El valor del número inicial del intervalo debe tener la misma longitud que el número final.</span><span class="sxs-lookup"><span data-stu-id="2f929-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>
    
- <span data-ttu-id="2f929-p104">El intervalo de números debe ser único. Este intervalo no se puede superponer a ningún otro.</span><span class="sxs-lookup"><span data-stu-id="2f929-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>
    
- <span data-ttu-id="2f929-119">Si el intervalo de números comienza con el carácter \* o #, el intervalo debe ser mayor que 100.</span><span class="sxs-lookup"><span data-stu-id="2f929-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>
    
- <span data-ttu-id="2f929-120">Valores válidos: debe coincidir con la cadena de expresión regular ([\\* | #] ?[1-9]\d{0,7}) | ([1-9] \d {0,8}).</span><span class="sxs-lookup"><span data-stu-id="2f929-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="2f929-121">Esto significa que el valor debe ser una cadena que comienza con el carácter de cualquier \* o # o un número del 1 al 9 (el primer carácter no puede ser cero).</span><span class="sxs-lookup"><span data-stu-id="2f929-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="2f929-122">Si el primer carácter es \* o #, el carácter siguiente debe ser un número del 1 al 9 (no puede ser cero).</span><span class="sxs-lookup"><span data-stu-id="2f929-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="2f929-123">Los caracteres siguientes pueden ser cualquier número del 0 al 9 hasta siete caracteres adicionales (por ejemplo, "#6000", "\*92000", "\*95551212" y "915551212").</span><span class="sxs-lookup"><span data-stu-id="2f929-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="2f929-124">Si el primer carácter no es \* o #, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido por un máximo de ocho caracteres, cada uno un número del 0 al 9 (por ejemplo, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="2f929-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>
    
### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="2f929-125">Para crear o modificar un intervalo del grupo de atención de llamadas</span><span class="sxs-lookup"><span data-stu-id="2f929-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="2f929-126">Inicie sesión en el equipo donde está instalado Skype para el Shell de administración de servidor empresarial como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios según se describe en **Configuración de permisos de delegado**.</span><span class="sxs-lookup"><span data-stu-id="2f929-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="2f929-127">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="2f929-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2f929-128">Utilice **CsCallParkOrbit de nuevo** para crear un nuevo rango de números de grupo recogida de llamada.</span><span class="sxs-lookup"><span data-stu-id="2f929-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="2f929-129">Utilice **Set CsCallParkOrbit** para modificar un rango existente de números de llamada de recogida.</span><span class="sxs-lookup"><span data-stu-id="2f929-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="2f929-130">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2f929-130">At the command line, run:</span></span>
    
   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="2f929-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2f929-131">For example:</span></span>
    
   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="2f929-132">En el siguiente ejemplo, se muestra cómo modificar un intervalo de números de órbitas de estacionamiento de llamadas a grupos de atención de llamadas.</span><span class="sxs-lookup"><span data-stu-id="2f929-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="2f929-133">Use este cmdlet para cambiar el tipo asignado a los intervalos de números únicamente si especificó el tipo incorrecto y el intervalo de números aún no se encuentra en uso.</span><span class="sxs-lookup"><span data-stu-id="2f929-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="2f929-134">Si cambia el intervalo de números de CallPark a GroupPickup, o viceversa, y este ya se encuentra en uso, el estacionamiento de llamadas o la atención de llamadas grupales dejará de funcionar para ese intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="2f929-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="2f929-135">Por ejemplo, si cambia un intervalo de números de CallPark a GroupPick, la aplicación de llamada Park ya no puede utilizar ese rango de las órbitas de llamadas park.</span><span class="sxs-lookup"><span data-stu-id="2f929-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2f929-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f929-136">See also</span></span>

#### 

[<span data-ttu-id="2f929-137">Nueva CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="2f929-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="2f929-138">Conjunto de CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="2f929-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="2f929-139">Eliminar un rango de órbita llamada Park</span><span class="sxs-lookup"><span data-stu-id="2f929-139">Delete a Call Park Orbit Range</span></span>](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

