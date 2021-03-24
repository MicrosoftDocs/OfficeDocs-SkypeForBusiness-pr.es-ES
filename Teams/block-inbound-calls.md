---
title: Bloquear llamadas entrantes en Microsoft Teams
ms.author: v-cichur
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: fcf50f96f352cfb72ff3bd700f2118c3cda51dd7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092868"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="2aaca-102">Bloquear llamadas entrantes</span><span class="sxs-lookup"><span data-stu-id="2aaca-102">Block inbound calls</span></span>

<span data-ttu-id="2aaca-103">Los planes de enrutamiento directo y llamadas del sistema telefónico admiten el bloqueo de llamadas entrantes desde la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="2aaca-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="2aaca-104">Esta característica permite definir una lista global de patrones de números de inquilino para que el identificador de llamada de todas las llamadas RTC entrantes al inquilino se pueda comprobar en la lista para obtener una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="2aaca-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="2aaca-105">Si se realiza una coincidencia, se rechaza una llamada entrante.</span><span class="sxs-lookup"><span data-stu-id="2aaca-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="2aaca-106">Esta característica de bloqueo de llamadas entrantes solo funciona en las llamadas entrantes que proceden de la RTC y solo funciona de forma global y empresarial.</span><span class="sxs-lookup"><span data-stu-id="2aaca-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="2aaca-107">No está disponible por usuario.</span><span class="sxs-lookup"><span data-stu-id="2aaca-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="2aaca-108">Los autores de llamadas bloqueados pueden experimentar comportamientos ligeramente diferentes cuando se han bloqueado.</span><span class="sxs-lookup"><span data-stu-id="2aaca-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="2aaca-109">El comportamiento se basa en cómo el operador del autor de la llamada bloqueado controla la notificación de que no se permite que la llamada se complete correctamente.</span><span class="sxs-lookup"><span data-stu-id="2aaca-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="2aaca-110">Algunos ejemplos pueden incluir un mensaje de operador que indica que la llamada no se puede completar como marcado, o simplemente soltar la llamada.</span><span class="sxs-lookup"><span data-stu-id="2aaca-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="2aaca-111">Información y controles de administración de bloqueo de llamadas</span><span class="sxs-lookup"><span data-stu-id="2aaca-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="2aaca-112">Los controles de administración para bloquear números solo se proporcionan con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2aaca-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="2aaca-113">Los patrones de bloque de números se definen como patrones de expresión regular.</span><span class="sxs-lookup"><span data-stu-id="2aaca-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="2aaca-114">El orden de las expresiones no es importante: el primer patrón coincidente en la lista da como resultado que la llamada se bloquee.</span><span class="sxs-lookup"><span data-stu-id="2aaca-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="2aaca-115">Un nuevo número o patrón que se agrega o quita en la lista de autores de llamadas bloqueados puede tardar hasta 24 horas en activarse.</span><span class="sxs-lookup"><span data-stu-id="2aaca-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="2aaca-116">Comandos de PowerShell de bloqueo de llamadas</span><span class="sxs-lookup"><span data-stu-id="2aaca-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="2aaca-117">Los patrones de número se administran con los cmdlets **New**, **Get**, **Set**, **Remove**  - **CsInboundBlockedNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="2aaca-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="2aaca-118">Puede administrar un patrón determinado con estos cmdlets, incluida la posibilidad de activar un patrón determinado.</span><span class="sxs-lookup"><span data-stu-id="2aaca-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="2aaca-119">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) devuelve una lista de todos los patrones de números bloqueados agregados a la lista de inquilinos, incluidos Nombre, Descripción, Habilitado (Verdadero/Falso) y Patrón para cada uno.</span><span class="sxs-lookup"><span data-stu-id="2aaca-119">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="2aaca-120">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) agrega un patrón de número bloqueado a la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="2aaca-120">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="2aaca-121">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) quita un patrón de número bloqueado de la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="2aaca-121">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="2aaca-122">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o varios parámetros de un patrón de número bloqueado en la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="2aaca-122">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="2aaca-123">Ver y activar toda la característica de bloqueo de llamadas se administra a través de los cmdlets **Get**, **Set**  - **CsTenantBlockingCallingNumbers.**</span><span class="sxs-lookup"><span data-stu-id="2aaca-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="2aaca-124">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) devuelve los parámetros de la lista global de números bloqueados, incluido Habilitado (Verdadero/Falso).</span><span class="sxs-lookup"><span data-stu-id="2aaca-124">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="2aaca-125">Hay una única directiva de inquilino global que no se puede modificar manualmente, aparte de activar o desactivar la característica.</span><span class="sxs-lookup"><span data-stu-id="2aaca-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="2aaca-126">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar las llamadas bloqueadas de inquilino global para que se puedan desactivar y desactivar en el nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="2aaca-126">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="2aaca-127">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2aaca-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="2aaca-128">Bloquear un número</span><span class="sxs-lookup"><span data-stu-id="2aaca-128">Block a number</span></span>

<span data-ttu-id="2aaca-129">En este ejemplo, los parámetros **Habilitado** y **Descripción** son opcionales.</span><span class="sxs-lookup"><span data-stu-id="2aaca-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="2aaca-130">La creación de un nuevo patrón agrega el patrón como habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2aaca-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="2aaca-131">La descripción es un campo opcional para proporcionar más información.</span><span class="sxs-lookup"><span data-stu-id="2aaca-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="2aaca-132">Le recomendamos que proporcione un nombre significativo para comprender fácilmente por qué se agregó el patrón.</span><span class="sxs-lookup"><span data-stu-id="2aaca-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="2aaca-133">En el caso de bloquear simplemente los números de correo no deseado, considere la posibilidad de asignar el mismo nombre a la regla que el patrón de número que se está haciendo coincidir y agregar información adicional en la descripción según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2aaca-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="2aaca-134">Los patrones coinciden con expresiones regulares (Regex).</span><span class="sxs-lookup"><span data-stu-id="2aaca-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="2aaca-135">Deje tiempo para la replicación antes de probar y validar.</span><span class="sxs-lookup"><span data-stu-id="2aaca-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="2aaca-136">Permitir un número</span><span class="sxs-lookup"><span data-stu-id="2aaca-136">Allow a number</span></span>

<span data-ttu-id="2aaca-137">En este ejemplo, se **requiere el** parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="2aaca-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="2aaca-138">Si no se conoce la identidad, use el cmdlet **Get-CsInboundBlockedNumberPattern** para localizar primero el patrón adecuado y anote la identidad.</span><span class="sxs-lookup"><span data-stu-id="2aaca-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="2aaca-139">A continuación, ejecute el cmdlet **Remove-CsTenantBlockedNumberPattern** y pase el valor de identidad adecuado.</span><span class="sxs-lookup"><span data-stu-id="2aaca-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="2aaca-140">Deje tiempo para la replicación antes de probar y validar.</span><span class="sxs-lookup"><span data-stu-id="2aaca-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="2aaca-141">Ver todos los patrones de números</span><span class="sxs-lookup"><span data-stu-id="2aaca-141">View all number patterns</span></span>

<span data-ttu-id="2aaca-142">Al ejecutar este cmdlet, se devuelve una lista de todos los números bloqueados que se introducen para un inquilino:</span><span class="sxs-lookup"><span data-stu-id="2aaca-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="2aaca-143">Use las capacidades de filtrado de PowerShell integradas para analizar los valores devueltos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2aaca-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="2aaca-144">Agregar excepciones de número</span><span class="sxs-lookup"><span data-stu-id="2aaca-144">Add number exceptions</span></span>

<span data-ttu-id="2aaca-145">Puede agregar excepciones a los patrones de números bloqueados mediante los cmdlets **New**, **Get**, **Set**, **Remove**  - **CsTenantBlockNumberExceptionPattern.**</span><span class="sxs-lookup"><span data-stu-id="2aaca-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="2aaca-146">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) agrega un patrón de excepción de número a la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="2aaca-146">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="2aaca-147">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) devuelve una lista de todos los patrones de excepción de número agregados a la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="2aaca-147">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="2aaca-148">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica uno o varios parámetros en un patrón de excepción de número en la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="2aaca-148">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="2aaca-149">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) quita un patrón de excepción de número de la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="2aaca-149">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="2aaca-150">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2aaca-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="2aaca-151">Agregar una excepción de número</span><span class="sxs-lookup"><span data-stu-id="2aaca-151">Add a number exception</span></span>

<span data-ttu-id="2aaca-152">En este ejemplo, se crea un nuevo patrón de excepción de número y, de forma predeterminada, se agregará el patrón como habilitado.</span><span class="sxs-lookup"><span data-stu-id="2aaca-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="2aaca-153">Los **parámetros Habilitado** y **Descripción** son opcionales.</span><span class="sxs-lookup"><span data-stu-id="2aaca-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="2aaca-154">Ver todas las excepciones de número</span><span class="sxs-lookup"><span data-stu-id="2aaca-154">View all number exceptions</span></span>

<span data-ttu-id="2aaca-155">En este ejemplo, el **parámetro Identity** es opcional.</span><span class="sxs-lookup"><span data-stu-id="2aaca-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="2aaca-156">Si no **se especifica** el parámetro Identity, este cmdlet devuelve una lista de todos los patrones de excepción de número especificados para un inquilino.</span><span class="sxs-lookup"><span data-stu-id="2aaca-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="2aaca-157">Modificar una excepción de número</span><span class="sxs-lookup"><span data-stu-id="2aaca-157">Modify a number exception</span></span>

<span data-ttu-id="2aaca-158">En este ejemplo, el **parámetro Identity** es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2aaca-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="2aaca-159">El cmdlet **Set-CsTenantBlockedNumberExceptionPattern** le permite modificar uno o varios parámetros para una identidad de patrón de número determinada.</span><span class="sxs-lookup"><span data-stu-id="2aaca-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="2aaca-160">Quitar una excepción de número</span><span class="sxs-lookup"><span data-stu-id="2aaca-160">Remove a number exception</span></span>

<span data-ttu-id="2aaca-161">En este ejemplo, se **requiere el** parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="2aaca-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="2aaca-162">Este cmdlet quitará el patrón de número dado de la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="2aaca-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="2aaca-163">Si no se conoce la identidad, use el cmdlet **Get-CsInboundBlockedNumberPattern** para localizar primero el patrón adecuado y anote la identidad.</span><span class="sxs-lookup"><span data-stu-id="2aaca-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="2aaca-164">A continuación, ejecute el cmdlet **Remove-CsTenantBlockedNumberExceptionPattern** y pase el valor de identidad adecuado.</span><span class="sxs-lookup"><span data-stu-id="2aaca-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="2aaca-165">Deje tiempo para la replicación antes de probar y validar.</span><span class="sxs-lookup"><span data-stu-id="2aaca-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="2aaca-166">Comprobar si un número está bloqueado</span><span class="sxs-lookup"><span data-stu-id="2aaca-166">Test whether a number is blocked</span></span>

<span data-ttu-id="2aaca-167">Use el cmdlet **Test-CsInboundBlockedNumberPattern** para comprobar si un número está bloqueado en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="2aaca-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="2aaca-168">En este ejemplo, los parámetros **PhoneNumber** y **Tenant** son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="2aaca-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="2aaca-169">El **parámetro PhoneNumber** debe ser una cadena numérica sin caracteres adicionales como + o -.</span><span class="sxs-lookup"><span data-stu-id="2aaca-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="2aaca-170">En TRPS, el parámetro **Inquilino** es opcional.</span><span class="sxs-lookup"><span data-stu-id="2aaca-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="2aaca-171">El parámetro **isNumberBlocked** resultante devuelve un valor de True si el número está bloqueado en el inquilino y False si no está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="2aaca-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="2aaca-172">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="2aaca-172">httpResponseCode</span></span>  |<span data-ttu-id="2aaca-173">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="2aaca-173">isNumberBlocked</span></span>   |<span data-ttu-id="2aaca-174">errorMessage</span><span class="sxs-lookup"><span data-stu-id="2aaca-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2aaca-175">200</span><span class="sxs-lookup"><span data-stu-id="2aaca-175">200</span></span>    | <span data-ttu-id="2aaca-176">Verdadero</span><span class="sxs-lookup"><span data-stu-id="2aaca-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="2aaca-177">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="2aaca-177">httpResponseCode</span></span>  |<span data-ttu-id="2aaca-178">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="2aaca-178">isNumberBlocked</span></span>   |<span data-ttu-id="2aaca-179">errorMessage</span><span class="sxs-lookup"><span data-stu-id="2aaca-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2aaca-180">200</span><span class="sxs-lookup"><span data-stu-id="2aaca-180">200</span></span>    | <span data-ttu-id="2aaca-181">Falso</span><span class="sxs-lookup"><span data-stu-id="2aaca-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="2aaca-182">Una nota sobre Regex</span><span class="sxs-lookup"><span data-stu-id="2aaca-182">A note about Regex</span></span>

<span data-ttu-id="2aaca-183">Como se indicó anteriormente, el patrón que coincide para bloquear las personas que llaman se realiza mediante Regex.</span><span class="sxs-lookup"><span data-stu-id="2aaca-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="2aaca-184">Hay varias herramientas disponibles en línea para ayudar a validar una coincidencia de patrón Regex.</span><span class="sxs-lookup"><span data-stu-id="2aaca-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="2aaca-185">Si no está familiarizado con los patrones Regex, le recomendamos que dedíciese a familiarizarse con los conceptos básicos.</span><span class="sxs-lookup"><span data-stu-id="2aaca-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="2aaca-186">Para asegurarse de que obtiene los resultados esperados, use una herramienta para validar las coincidencias de patrón antes de agregar nuevas coincidencias de números bloqueados al inquilino.</span><span class="sxs-lookup"><span data-stu-id="2aaca-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>