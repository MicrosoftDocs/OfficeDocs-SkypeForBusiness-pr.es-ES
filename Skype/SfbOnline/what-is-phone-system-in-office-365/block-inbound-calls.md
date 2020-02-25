---
title: Bloquear llamadas entrantes en Skype empresarial online
ms.author: v-lanac
author: lanachin
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: b238d69087c5b29e6d9abc898e91c44fd8053411
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266073"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="d5d00-102">Bloquear llamadas entrantes</span><span class="sxs-lookup"><span data-stu-id="d5d00-102">Block inbound calls</span></span>

<span data-ttu-id="d5d00-103">Ahora, los planes de llamadas de Skype empresarial online admiten el bloqueo de llamadas entrantes desde la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="d5d00-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="d5d00-104">Esta característica permite que se defina una lista global de inquilinos de patrones de números para que la identificación de llamadas de todas las llamadas RTC entrantes en el inquilino se pueda comprobar con la lista en busca de una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="d5d00-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="d5d00-105">Si se realiza una coincidencia, se rechaza una llamada entrante.</span><span class="sxs-lookup"><span data-stu-id="d5d00-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="d5d00-106">Esta característica de bloqueo de llamadas entrantes solo funciona en llamadas entrantes que se originan desde la RTC y solo funciona con un inquilino global.</span><span class="sxs-lookup"><span data-stu-id="d5d00-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="d5d00-107">No está disponible para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="d5d00-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="d5d00-108">Esta característica aún no está disponible para el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="d5d00-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="d5d00-109">Los autores de llamadas bloqueados pueden experimentar comportamientos ligeramente diferentes cuando se han bloqueado.</span><span class="sxs-lookup"><span data-stu-id="d5d00-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="d5d00-110">El comportamiento se basa en la forma en que el portador de la persona que llama bloqueada controla la notificación de que la llamada no se puede completar correctamente.</span><span class="sxs-lookup"><span data-stu-id="d5d00-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="d5d00-111">Es posible que algunos ejemplos incluyan un mensaje que indica que la llamada no se puede completar como marcando o simplemente se encuentra en la llamada.</span><span class="sxs-lookup"><span data-stu-id="d5d00-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="d5d00-112">Información y controles de administración con bloqueo de llamadas</span><span class="sxs-lookup"><span data-stu-id="d5d00-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="d5d00-113">Los controles de administración para números de bloqueo se proporcionan con PowerShell solo.</span><span class="sxs-lookup"><span data-stu-id="d5d00-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="d5d00-114">Los patrones de bloques de números se definen como patrones de expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="d5d00-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="d5d00-115">El orden de las expresiones no es importante, el primer patrón que coincide en la lista provoca la bloqueo de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d5d00-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="d5d00-116">Un nuevo número o patrón que se agrega o se elimina en la lista de llamadas bloqueadas puede demorar hasta 24 horas para que el patrón se active.</span><span class="sxs-lookup"><span data-stu-id="d5d00-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="d5d00-117">Comandos de PowerShell de bloqueo de llamadas</span><span class="sxs-lookup"><span data-stu-id="d5d00-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="d5d00-118">Los patrones de número se administran ```New```a ```Get```través ```Set```de los ```Remove``` ```CsInboundBlockedNumberPattern``` comandos,,, y.</span><span class="sxs-lookup"><span data-stu-id="d5d00-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="d5d00-119">Puede administrar un patrón determinado con estos cmdlets, incluida la capacidad de activar o desactivar la activación de un patrón determinado.</span><span class="sxs-lookup"><span data-stu-id="d5d00-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="d5d00-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) devuelve una lista de todos los patrones de números bloqueados agregados a la lista de inquilinos, como nombre, descripción, habilitado (verdadero/falso) y patrón para cada uno.</span><span class="sxs-lookup"><span data-stu-id="d5d00-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="d5d00-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) agrega un patrón de números bloqueados a la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d5d00-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="d5d00-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) quita un patrón de números bloqueados de la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d5d00-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="d5d00-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o más parámetros de un patrón de número bloqueado en la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d5d00-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="d5d00-124">La visualización y activación de toda la característica de bloqueo de llamadas ```CsTenantBlockingCallingNumbers``` se ```Get``` administra ```Set```a través de los comandos y.</span><span class="sxs-lookup"><span data-stu-id="d5d00-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="d5d00-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) devuelve los parámetros de la lista global de números bloqueados, que incluye Enabled (verdadero/falso).</span><span class="sxs-lookup"><span data-stu-id="d5d00-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="d5d00-126">Hay una única directiva de inquilino global que no se puede modificar de forma manual salvo para activar o desactivar la característica.</span><span class="sxs-lookup"><span data-stu-id="d5d00-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="d5d00-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar las llamadas de inquilino global bloqueadas y desactivadas en el nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="d5d00-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="d5d00-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d5d00-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="d5d00-129">Bloquear un número</span><span class="sxs-lookup"><span data-stu-id="d5d00-129">Block a number</span></span>

<span data-ttu-id="d5d00-130">En este ejemplo, los ```-Enabled``` parámetros ```-Description``` y son opcionales:</span><span class="sxs-lookup"><span data-stu-id="d5d00-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="d5d00-131">La creación de un nuevo patrón agrega el patrón como habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d5d00-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="d5d00-132">La descripción es un campo opcional para proporcionar más información.</span><span class="sxs-lookup"><span data-stu-id="d5d00-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="d5d00-133">Le recomendamos que proporcione un nombre significativo para comprender fácilmente por qué se agregó el patrón.</span><span class="sxs-lookup"><span data-stu-id="d5d00-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="d5d00-134">En el caso de simplemente bloquear los números de correo no deseado, considere la posibilidad de nombrar la regla como el patrón de número que se está cotejando y agregue información adicional en la descripción según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d5d00-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="d5d00-135">Los patrones coinciden con expresiones regulares (regex).</span><span class="sxs-lookup"><span data-stu-id="d5d00-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="d5d00-136">Deje tiempo para la replicación antes de probar y validar.</span><span class="sxs-lookup"><span data-stu-id="d5d00-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="d5d00-137">Permitir un número</span><span class="sxs-lookup"><span data-stu-id="d5d00-137">Allow a number</span></span>

<span data-ttu-id="d5d00-138">En este ejemplo, se ```-Identity``` requiere el parámetro:</span><span class="sxs-lookup"><span data-stu-id="d5d00-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="d5d00-139">Si no se conoce la identidad, use ```Get-CsInboundBlockedNumberPattern``` el cmdlet para ubicar primero el patrón adecuado y anote la identidad.</span><span class="sxs-lookup"><span data-stu-id="d5d00-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="d5d00-140">A continuación, ejecute ```Remove-CsTenantBlockedNumberPattern``` el cmdlet y pase el valor de identidad adecuado.</span><span class="sxs-lookup"><span data-stu-id="d5d00-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="d5d00-141">Deje tiempo para la replicación antes de probar y validar.</span><span class="sxs-lookup"><span data-stu-id="d5d00-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="d5d00-142">Ver todos los patrones de números</span><span class="sxs-lookup"><span data-stu-id="d5d00-142">View all number patterns</span></span>

<span data-ttu-id="d5d00-143">La ejecución de este cmdlet devuelve una lista de todos los números bloqueados que se especifican para un inquilino:</span><span class="sxs-lookup"><span data-stu-id="d5d00-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="d5d00-144">Use las capacidades de filtrado de PowerShell integradas para analizar los valores devueltos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d5d00-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="d5d00-145">Agregar excepciones de número</span><span class="sxs-lookup"><span data-stu-id="d5d00-145">Add number exceptions</span></span>

<span data-ttu-id="d5d00-146">Puede Agregar excepciones a patrones de números bloqueados mediante ```CsTenantBlockNumberExceptionPattern``` los comandos ```New```, ```Get```, ```Set```,, ```Remove```y.</span><span class="sxs-lookup"><span data-stu-id="d5d00-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="d5d00-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) agrega un patrón de excepción de número a la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d5d00-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="d5d00-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) devuelve una lista de todos los patrones de excepción de los números agregados a la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d5d00-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="d5d00-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica uno o más parámetros a un patrón de excepción de número en la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d5d00-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="d5d00-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) quita un patrón de excepción de número de la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d5d00-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="d5d00-151">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d5d00-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="d5d00-152">Agregar una excepción de número</span><span class="sxs-lookup"><span data-stu-id="d5d00-152">Add a number exception</span></span>

<span data-ttu-id="d5d00-153">En este ejemplo, se crea un patrón de excepción de número nuevo y, de forma predeterminada, agregará el patrón como habilitado.</span><span class="sxs-lookup"><span data-stu-id="d5d00-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="d5d00-154">Los ```-Enabled``` parámetros ```-Description``` y son opcionales.</span><span class="sxs-lookup"><span data-stu-id="d5d00-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="d5d00-155">Ver todas las excepciones de números</span><span class="sxs-lookup"><span data-stu-id="d5d00-155">View all number exceptions</span></span>

<span data-ttu-id="d5d00-156">En este ejemplo, el parámetro-Identity es opcional.</span><span class="sxs-lookup"><span data-stu-id="d5d00-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="d5d00-157">Si no ```-Identity``` se especifica el parámetro, este cmdlet devuelve una lista de todos los patrones de excepción de número especificados para un inquilino.</span><span class="sxs-lookup"><span data-stu-id="d5d00-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="d5d00-158">Modificar una excepción de número</span><span class="sxs-lookup"><span data-stu-id="d5d00-158">Modify a number exception</span></span>

<span data-ttu-id="d5d00-159">En este ejemplo, el parámetro-Identity es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d5d00-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="d5d00-160">El ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet te permite modificar uno o más parámetros para una identidad de patrón de número determinada.</span><span class="sxs-lookup"><span data-stu-id="d5d00-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="d5d00-161">Quitar una excepción de número</span><span class="sxs-lookup"><span data-stu-id="d5d00-161">Remove a number exception</span></span>

<span data-ttu-id="d5d00-162">En este ejemplo, se ```-Identity``` requiere el parámetro.</span><span class="sxs-lookup"><span data-stu-id="d5d00-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="d5d00-163">Este cmdlet quitará el patrón de número dado de la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d5d00-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="d5d00-164">Si no se conoce la identidad, use ```Get-CsInboundBlockedNumberPattern``` el cmdlet para ubicar primero el patrón adecuado y anote la identidad.</span><span class="sxs-lookup"><span data-stu-id="d5d00-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="d5d00-165">A continuación, ejecute ```Remove-CsTenantBlockedNumberExceptionPattern``` el cmdlet y pase el valor de identidad adecuado.</span><span class="sxs-lookup"><span data-stu-id="d5d00-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="d5d00-166">Deje tiempo para la replicación antes de probar y validar.</span><span class="sxs-lookup"><span data-stu-id="d5d00-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="d5d00-167">Comprobar si un número está bloqueado</span><span class="sxs-lookup"><span data-stu-id="d5d00-167">Test whether a number is blocked</span></span>

<span data-ttu-id="d5d00-168">Use el ```Test-CsInboundBlockedNumberPattern``` cmdlet para comprobar si un número está bloqueado en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="d5d00-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="d5d00-169">En este ejemplo, los ```-Phonenumber``` parámetros ```-Tenant``` and son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="d5d00-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="d5d00-170">El ```-PhoneNumber``` parámetro debe ser una cadena numérica sin caracteres adicionales, como + o-.</span><span class="sxs-lookup"><span data-stu-id="d5d00-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="d5d00-171">En TRPS, el ```-Tenant parameter``` es opcional.</span><span class="sxs-lookup"><span data-stu-id="d5d00-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="d5d00-172">El parámetro ```isNumberBlocked``` resultante devuelve un valor de verdadero si el número está bloqueado en el inquilino y falso si no está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="d5d00-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="d5d00-173">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="d5d00-173">httpResponseCode</span></span>  |<span data-ttu-id="d5d00-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="d5d00-174">isNumberBlocked</span></span>   |<span data-ttu-id="d5d00-175">errorMessage</span><span class="sxs-lookup"><span data-stu-id="d5d00-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d5d00-176">200</span><span class="sxs-lookup"><span data-stu-id="d5d00-176">200</span></span>    | <span data-ttu-id="d5d00-177">Verdadero</span><span class="sxs-lookup"><span data-stu-id="d5d00-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="d5d00-178">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="d5d00-178">httpResponseCode</span></span>  |<span data-ttu-id="d5d00-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="d5d00-179">isNumberBlocked</span></span>   |<span data-ttu-id="d5d00-180">errorMessage</span><span class="sxs-lookup"><span data-stu-id="d5d00-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d5d00-181">200</span><span class="sxs-lookup"><span data-stu-id="d5d00-181">200</span></span>    | <span data-ttu-id="d5d00-182">Falso</span><span class="sxs-lookup"><span data-stu-id="d5d00-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="d5d00-183">Una nota sobre Regex</span><span class="sxs-lookup"><span data-stu-id="d5d00-183">A note about Regex</span></span>

<span data-ttu-id="d5d00-184">Como se indicó anteriormente, la coincidencia de patrones para las personas que llaman se realiza usando Regex.</span><span class="sxs-lookup"><span data-stu-id="d5d00-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="d5d00-185">Hay varias herramientas disponibles en línea para ayudar a validar una coincidencia de patrón de Regex.</span><span class="sxs-lookup"><span data-stu-id="d5d00-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="d5d00-186">Si no está familiarizado con los patrones de Regex, le recomendamos que tome algún tiempo para familiarizarse con los conceptos básicos.</span><span class="sxs-lookup"><span data-stu-id="d5d00-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="d5d00-187">Para asegurarse de que obtiene los resultados esperados, use una herramienta para validar las coincidencias de modelos antes de agregar nuevas coincidencias de número bloqueado a su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="d5d00-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="d5d00-188">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d5d00-188">Related topics</span></span>

- [<span data-ttu-id="d5d00-189">Configurar el equipo para administrar Skype empresarial online mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5d00-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
