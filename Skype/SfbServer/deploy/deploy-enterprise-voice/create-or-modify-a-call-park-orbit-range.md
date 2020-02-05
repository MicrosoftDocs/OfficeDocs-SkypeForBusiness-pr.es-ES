---
title: Crear o modificar un intervalo de llamada de Parque orbital en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Crear o modificar una tabla de intervalos orbitar de llamadas en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: a5df3b61baf66a09bf968daf5c088e1c2ebf5734
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767903"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="a9a14-103">Crear o modificar un intervalo de llamada de Parque orbital en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="a9a14-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="a9a14-104">Crear o modificar una tabla de intervalos orbitar de llamadas en Skype empresarial Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="a9a14-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="a9a14-105">El parque de llamadas usa órbitas para hacer llamadas de aparcamiento.</span><span class="sxs-lookup"><span data-stu-id="a9a14-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="a9a14-106">Para que los usuarios puedan detener y recuperar llamadas, debe configurar la tabla de llamadas de la órbita de estacionamiento.</span><span class="sxs-lookup"><span data-stu-id="a9a14-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="a9a14-107">Debe especificar los intervalos de números de extensión (órbitas) que la organización reservará para las llamadas de aparcamiento y definir la distribución de esos intervalos especificando qué grupo de estacionamiento de llamadas controla cada rango.</span><span class="sxs-lookup"><span data-stu-id="a9a14-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="a9a14-108">A la hora de definir intervalos de órbitas, el objetivo es tener una cantidad suficiente de órbitas, de modo que ninguna de las órbitas vuelva a usarse en seguida; con todo, tampoco se deben tener demasiadas órbitas porque esto limitaría el número de extensiones disponibles para los usuarios u otros servicios.</span><span class="sxs-lookup"><span data-stu-id="a9a14-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="a9a14-109">Puede crear varios intervalos órbitas de estacionamiento de llamadas para cada grupo de servidores de Skype empresarial en el que se implemente la aplicación de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a9a14-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="a9a14-110">Cada intervalo de estacionamiento de llamadas debe tener un nombre único global y un conjunto único de extensiones.</span><span class="sxs-lookup"><span data-stu-id="a9a14-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9a14-p102">Un intervalo de órbitas suele estar formado por 100 órbitas o menos, pero puede ser mucho mayor, siempre que tenga menos de 10 000 órbitas (número máximo) por intervalo y que usted tenga menos de 50 000 órbitas por grupo de servidores. Si un intervalo es demasiado pequeño, las órbitas se volverán a usar con mayor rapidez.</span><span class="sxs-lookup"><span data-stu-id="a9a14-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="a9a14-114">Use bloques de extensiones virtuales (extensiones que no tengan asignado ningún usuario ni teléfono) para los intervalos de órbitas.</span><span class="sxs-lookup"><span data-stu-id="a9a14-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="a9a14-115">No se admite la asignación de números de marcación directa (hecho) como números en órbita en la tabla de llamadas en órbita de estacionamiento.</span><span class="sxs-lookup"><span data-stu-id="a9a14-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="a9a14-116">Use los siguientes procedimientos para crear o modificar un intervalo de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a9a14-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="a9a14-117">Para usar el panel de control de Skype empresarial Server para crear o modificar un intervalo de números para las llamadas de aparcamiento</span><span class="sxs-lookup"><span data-stu-id="a9a14-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="a9a14-p103">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="a9a14-p103">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="a9a14-120">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a9a14-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="a9a14-121">En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Estacionamiento de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="a9a14-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="a9a14-122">En la página **Estacionamiento de llamadas**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="a9a14-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="a9a14-p104">Para crear un nuevo intervalo de órbitas, haga clic en **Nuevo**. En **Nombre**, escriba un nombre identificativo para este intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="a9a14-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="a9a14-125">Una vez que haya confirmado el intervalo de órbitas para la base de datos, no podrá cambiar este nombre.</span><span class="sxs-lookup"><span data-stu-id="a9a14-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="a9a14-p105">Para modificar un intervalo de órbitas existente, escriba todo o parte del nombre del intervalo de órbitas en el campo de búsqueda. En la lista de órbitas resultante, haga clic en la órbita que desee, seleccione **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="a9a14-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="a9a14-128">En el primer campo **Intervalo numérico**, escriba el número inicial del intervalo de extensiones para esta órbita de estacionamiento de llamadas y, en el segundo campo **Intervalo numérico**, escriba el número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="a9a14-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="a9a14-129">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9a14-129">Be aware:</span></span>

   - <span data-ttu-id="a9a14-130">El número inicial del intervalo debe ser menor o igual al número final.</span><span class="sxs-lookup"><span data-stu-id="a9a14-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="a9a14-131">El valor del número inicial del intervalo debe tener la misma longitud que el número final.</span><span class="sxs-lookup"><span data-stu-id="a9a14-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="a9a14-p107">El intervalo de órbitas debe ser único. Este intervalo no se puede superponer con ningún otro.</span><span class="sxs-lookup"><span data-stu-id="a9a14-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="a9a14-134">Si el intervalo de órbita comienza con el \* carácter o #, el intervalo debe ser mayor que 100.</span><span class="sxs-lookup"><span data-stu-id="a9a14-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="a9a14-135">Valores válidos: deben coincidir con la cadena de\\expresión regular ([\* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="a9a14-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="a9a14-136">Esto significa que el valor debe ser una cadena que comienza con el \* carácter o # o un número 1 a 9 (el primer carácter no puede ser un cero).</span><span class="sxs-lookup"><span data-stu-id="a9a14-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="a9a14-137">Si el primer carácter es \* o #, el siguiente carácter debe ser un número del 1 al 9 (no puede ser un cero).</span><span class="sxs-lookup"><span data-stu-id="a9a14-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="a9a14-138">Los siguientes caracteres pueden ser del 0 al 9 hasta siete caracteres adicionales (por ejemplo, "#6000", "\*92000", "\*95551212" y "915551212").</span><span class="sxs-lookup"><span data-stu-id="a9a14-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="a9a14-139">Si el primer carácter no \* es o #, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido de hasta ocho caracteres, cada uno de los números del 0 al 9 (por ejemplo, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="a9a14-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="a9a14-p109">No debe tener más de 50 000 órbitas por grupo de servidores. Cada intervalo de órbitas normalmente está formado por 100 órbitas o menos, pero puede ser mucho mayor siempre que tenga menos de 10 000 órbitas. Por ejemplo, en lugar de especificar un número de inicio de "7000000" y un número de finalización de "8000000", piense en especificar un número de inicio de "7000000" y un número de finalización de "7000100".</span><span class="sxs-lookup"><span data-stu-id="a9a14-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="a9a14-143">En **FQDN del servidor de destino**, haga clic en el nombre de dominio completo (FQDN) o el identificador de servicio del servicio de aplicación que hospeda la aplicación de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a9a14-143">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="a9a14-144">Todas las llamadas estacionadas en números del intervalo especificado por el número de inicio y el número de finalización de cada intervalo de órbitas se enrutarán a este servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a9a14-144">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="a9a14-145">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a9a14-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="a9a14-146">Para usar el shell de administración de Skype empresarial para crear o modificar un intervalo de números para las llamadas de aparcamiento</span><span class="sxs-lookup"><span data-stu-id="a9a14-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="a9a14-147">Inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, como se describe en **permisos de configuración de delegado**.</span><span class="sxs-lookup"><span data-stu-id="a9a14-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="a9a14-148">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="a9a14-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="a9a14-149">Use **New-CsCallParkOrbit** para crear un nuevo intervalo de números de órbitas.</span><span class="sxs-lookup"><span data-stu-id="a9a14-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="a9a14-150">Use **Set-CsCallParkOrbit** para modificar un intervalo de números de órbitas existente.</span><span class="sxs-lookup"><span data-stu-id="a9a14-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="a9a14-151">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="a9a14-151">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="a9a14-152">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a9a14-152">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="a9a14-153">En el ejemplo siguiente se muestra cómo modificar los números de un intervalos de órbitas existente,</span><span class="sxs-lookup"><span data-stu-id="a9a14-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="a9a14-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9a14-154">See also</span></span>

[<span data-ttu-id="a9a14-155">Nuevo: CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="a9a14-155">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="a9a14-156">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="a9a14-156">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="a9a14-157">Eliminar un intervalo orbitar de llamada</span><span class="sxs-lookup"><span data-stu-id="a9a14-157">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
