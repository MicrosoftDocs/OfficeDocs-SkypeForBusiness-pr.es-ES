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
ms.openlocfilehash: e584e9f0c16ef77424121c37ce87c6d63afb4b92
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689768"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="ce495-102">Bloquear llamadas entrantes</span><span class="sxs-lookup"><span data-stu-id="ce495-102">Block inbound calls</span></span>

<span data-ttu-id="ce495-103">Los planes de llamadas de Microsoft, el enrutamiento directo y el operador Conectar todas las llamadas entrantes de la red telefónica conmutada (RTC) pública.</span><span class="sxs-lookup"><span data-stu-id="ce495-103">Microsoft Calling Plans, Direct Routing, and Operator Connect all support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="ce495-104">Esta característica permite a un administrador definir una lista de patrones de número en el nivel global del inquilino para que el identificador de llamada de todas las llamadas RTC entrantes al inquilino se pueda comprobar en la lista para obtener una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="ce495-104">This feature allows an administrator to define a  list of number patterns at the tenant global level so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="ce495-105">Si se realiza una coincidencia, se rechaza una llamada entrante.</span><span class="sxs-lookup"><span data-stu-id="ce495-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="ce495-106">Esta característica de bloqueo de llamadas entrantes solo funciona en las llamadas entrantes que proceden de la RTC y solo funciona en un nivel global de inquilino.</span><span class="sxs-lookup"><span data-stu-id="ce495-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant global level.</span></span> <span data-ttu-id="ce495-107">Los Teams usuarios no pueden manipular esta lista.</span><span class="sxs-lookup"><span data-stu-id="ce495-107">Individual Teams users can’t manipulate this list.</span></span> <span data-ttu-id="ce495-108">El Teams permite a los usuarios individuales bloquear llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="ce495-108">The Teams client does allow individual users to block PSTN calls.</span></span> <span data-ttu-id="ce495-109">Para obtener información sobre cómo los usuarios finales pueden implementar el bloqueo de llamadas, vea Administrar la configuración de llamadas [en Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span><span class="sxs-lookup"><span data-stu-id="ce495-109">For information about how your end users can implement call blocking, see [Manage call settings in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span>

>[!NOTE]
> <span data-ttu-id="ce495-110">Los autores de llamadas bloqueados pueden experimentar comportamientos ligeramente diferentes cuando se han bloqueado.</span><span class="sxs-lookup"><span data-stu-id="ce495-110">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="ce495-111">El comportamiento se basa en cómo el operador del autor de la llamada bloqueado controla la notificación de que no se permite que la llamada se complete correctamente.</span><span class="sxs-lookup"><span data-stu-id="ce495-111">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="ce495-112">Algunos ejemplos pueden incluir un mensaje de operador que indica que la llamada no se puede completar como marcado, o simplemente soltar la llamada.</span><span class="sxs-lookup"><span data-stu-id="ce495-112">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="ce495-113">Información y controles de administración de bloqueo de llamadas</span><span class="sxs-lookup"><span data-stu-id="ce495-113">Call blocking admin controls and information</span></span>

<span data-ttu-id="ce495-114">Los controles de administración para bloquear números solo se proporcionan con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce495-114">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="ce495-115">Los patrones de bloque de números se definen como patrones de expresión regular.</span><span class="sxs-lookup"><span data-stu-id="ce495-115">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="ce495-116">El orden de las expresiones no es importante: el primer patrón coincidente en la lista da como resultado que la llamada se bloquee.</span><span class="sxs-lookup"><span data-stu-id="ce495-116">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="ce495-117">Un nuevo número o patrón que se agrega o quita en la lista de autores de llamadas bloqueados puede tardar hasta 24 horas en activarse.</span><span class="sxs-lookup"><span data-stu-id="ce495-117">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="ce495-118">Comandos de PowerShell de bloqueo de llamadas</span><span class="sxs-lookup"><span data-stu-id="ce495-118">Call blocking PowerShell commands</span></span>

<span data-ttu-id="ce495-119">Los patrones de número se administran con los cmdlets **New-**, **Get-**, **Set-** y **Remove-CsInboundBlockedNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="ce495-119">You manage number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="ce495-120">Puede administrar un patrón determinado con estos cmdlets, incluida la posibilidad de activar un patrón determinado.</span><span class="sxs-lookup"><span data-stu-id="ce495-120">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="ce495-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) devuelve una lista de todos los patrones de números bloqueados agregados a la lista de inquilinos, incluidos Nombre, Descripción, Habilitado (Verdadero/Falso) y Patrón para cada uno.</span><span class="sxs-lookup"><span data-stu-id="ce495-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="ce495-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) agrega un patrón de número bloqueado a la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="ce495-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="ce495-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) quita un patrón de número bloqueado de la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="ce495-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="ce495-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o varios parámetros de un patrón de número bloqueado en la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="ce495-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="ce495-125">Ver y activar toda la característica de bloqueo de llamadas se administra a través de los cmdlets **Get y** **Set-CsTenantBlockingCallingNumbers.**</span><span class="sxs-lookup"><span data-stu-id="ce495-125">Viewing and activating the entire call blocking feature is managed through the **Get-** and **Set-CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="ce495-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) devuelve los patrones de número de bloque de entrada y los parámetros de patrones de números exentos de entrada para la lista global de números bloqueados.</span><span class="sxs-lookup"><span data-stu-id="ce495-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the inbound block number patterns and the inbound exempt number patterns parameters for the global blocked number list.</span></span> <span data-ttu-id="ce495-127">Este cmdlet también devuelve si el bloqueo se ha habilitado (Verdadero o Falso).</span><span class="sxs-lookup"><span data-stu-id="ce495-127">This cmdlet also returns whether blocking has been Enabled (True or False).</span></span> <span data-ttu-id="ce495-128">Hay una única directiva de inquilino global que no se puede modificar manualmente, aparte de activar o desactivar la característica.</span><span class="sxs-lookup"><span data-stu-id="ce495-128">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="ce495-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar las llamadas bloqueadas de inquilino global para que se puedan desactivar y desactivar en el nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="ce495-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="ce495-130">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ce495-130">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="ce495-131">Bloquear un número</span><span class="sxs-lookup"><span data-stu-id="ce495-131">Block a number</span></span>

<span data-ttu-id="ce495-132">En el siguiente ejemplo, el administrador de inquilinos quiere bloquear todas las llamadas procedentes del rango de números 1 (312) 555-0000 a 1 (312) 555-9999.</span><span class="sxs-lookup"><span data-stu-id="ce495-132">In the following example, the tenant administrator wants to block all calls coming from the number range 1 (312) 555-0000 to 1 (312) 555-9999.</span></span> <span data-ttu-id="ce495-133">Se crea el patrón de números para que ambos números del rango con + prefijo y los números del rango sin + prefijo coincidan.</span><span class="sxs-lookup"><span data-stu-id="ce495-133">The number pattern is created so that both numbers in range with + prefixed and numbers in the range without + prefixed are matched.</span></span> <span data-ttu-id="ce495-134">No es necesario incluir los símbolos y () en los números de teléfono porque el sistema los quita antes de hacer coincidir.</span><span class="sxs-lookup"><span data-stu-id="ce495-134">You don’t need to include the symbols – and () in the phone numbers because the system strips these symbols before matching.</span></span>  <span data-ttu-id="ce495-135">Para activar el patrón de números, el **parámetro Enabled** se establece en True.</span><span class="sxs-lookup"><span data-stu-id="ce495-135">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="ce495-136">Para deshabilitar este patrón de número específico, establezca el parámetro en Falso.</span><span class="sxs-lookup"><span data-stu-id="ce495-136">To disable this specific number pattern, set the parameter to False.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

<span data-ttu-id="ce495-137">En el siguiente ejemplo, el administrador de inquilinos quiere bloquear todas las llamadas procedentes del número 1 (412) 555-1234.</span><span class="sxs-lookup"><span data-stu-id="ce495-137">In the next example, the tenant administrator wants to block all calls coming from the number 1 (412) 555-1234.</span></span> <span data-ttu-id="ce495-138">Para activar el patrón de números, el **parámetro Enabled** se establece en True.</span><span class="sxs-lookup"><span data-stu-id="ce495-138">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

<span data-ttu-id="ce495-139">La creación de un nuevo patrón agrega el patrón como habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ce495-139">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="ce495-140">La descripción es un campo opcional para proporcionar más información.</span><span class="sxs-lookup"><span data-stu-id="ce495-140">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="ce495-141">Le recomendamos que proporcione un nombre significativo para comprender fácilmente por qué se agregó el patrón.</span><span class="sxs-lookup"><span data-stu-id="ce495-141">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="ce495-142">En el caso de bloquear simplemente los números de correo no deseado, considere la posibilidad de asignar el mismo nombre a la regla que el patrón de número que se está haciendo coincidir y agregar información adicional en la descripción según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ce495-142">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="ce495-143">Los patrones coinciden con expresiones regulares (Regex).</span><span class="sxs-lookup"><span data-stu-id="ce495-143">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="ce495-144">Para obtener más información, vea [Usar Regex](#using-regex).</span><span class="sxs-lookup"><span data-stu-id="ce495-144">For more information, see [Using Regex](#using-regex).</span></span>

<span data-ttu-id="ce495-145">Deje tiempo para la replicación antes de probar y validar.</span><span class="sxs-lookup"><span data-stu-id="ce495-145">Allow time for replication before you test and validate.</span></span> 

#### <a name="allow-a-number"></a><span data-ttu-id="ce495-146">Permitir un número</span><span class="sxs-lookup"><span data-stu-id="ce495-146">Allow a number</span></span>

<span data-ttu-id="ce495-147">Puede permitir que un número llame quitando el patrón de número bloqueado.</span><span class="sxs-lookup"><span data-stu-id="ce495-147">You can allow a number to call by removing the blocked number pattern.</span></span> <span data-ttu-id="ce495-148">En el siguiente ejemplo, el administrador de inquilinos quiere permitir que 1 (412) 555-1234 vuelva a realizar llamadas.</span><span class="sxs-lookup"><span data-stu-id="ce495-148">In the following example, the tenant administrator wants to allow 1 (412) 555-1234 to make calls again.</span></span>

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
<span data-ttu-id="ce495-149">Si no se conoce la identidad, use el cmdlet **Get-CsInboundBlockedNumberPattern** para localizar primero el patrón adecuado y anote la identidad.</span><span class="sxs-lookup"><span data-stu-id="ce495-149">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="ce495-150">Después, ejecute el cmdlet **Remove-CsInboundBlockedNumberPattern** y pase el valor de identidad adecuado.</span><span class="sxs-lookup"><span data-stu-id="ce495-150">Then, run the **Remove-CsInboundBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="ce495-151">Deje tiempo para la replicación antes de probar y validar.</span><span class="sxs-lookup"><span data-stu-id="ce495-151">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="ce495-152">Ver todos los patrones de números</span><span class="sxs-lookup"><span data-stu-id="ce495-152">View all number patterns</span></span>

<span data-ttu-id="ce495-153">Al ejecutar este cmdlet, se devuelve una lista de todos los números bloqueados que se introducen para un inquilino:</span><span class="sxs-lookup"><span data-stu-id="ce495-153">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="ce495-154">Use las capacidades de filtrado de PowerShell integradas para analizar los valores devueltos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ce495-154">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="ce495-155">Agregar excepciones de número</span><span class="sxs-lookup"><span data-stu-id="ce495-155">Add number exceptions</span></span>

<span data-ttu-id="ce495-156">Puede agregar excepciones a los patrones de números bloqueados mediante los cmdlets **New-**, **Get-**, **Set-** y **Remove-CsInboundExemptNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="ce495-156">You can add exceptions to blocked number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundExemptNumberPattern** cmdlets.</span></span>

- <span data-ttu-id="ce495-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) agrega un patrón de excepción de número a la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="ce495-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="ce495-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) devuelve una lista de todos los patrones de excepción de número agregados a la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="ce495-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="ce495-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifica uno o varios parámetros en un patrón de excepción de número en la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="ce495-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="ce495-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) quita un patrón de excepción de número de la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="ce495-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="ce495-161">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ce495-161">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="ce495-162">Agregar una excepción de número</span><span class="sxs-lookup"><span data-stu-id="ce495-162">Add a number exception</span></span>

<span data-ttu-id="ce495-163">En el ejemplo siguiente, el administrador de inquilinos desea permitir que los números de teléfono 1 (312) 555-8882 y 1 (312) 555-8883 realicen llamadas al inquilino, incluso si estos dos números de teléfono están en el rango que se ha bloqueado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="ce495-163">In the following example, the tenant administrator wants to allow the phone numbers 1 (312) 555-8882 and 1 (312) 555-8883 to make calls to the tenant, even if these two phone numbers are in the range that has been blocked in the example above.</span></span> <span data-ttu-id="ce495-164">Para habilitar esta opción, se crea un nuevo patrón de excepción de número de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ce495-164">To enable this, a new number exception pattern is created as follows:</span></span>

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

<span data-ttu-id="ce495-165">Para activar el patrón de números, el **parámetro Enabled** se establece en True.</span><span class="sxs-lookup"><span data-stu-id="ce495-165">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="ce495-166">Para deshabilitar este patrón de número específico, establezca el parámetro en Falso.</span><span class="sxs-lookup"><span data-stu-id="ce495-166">To disable this specific number pattern, set the parameter to False.</span></span>


#### <a name="view-all-number-exceptions"></a><span data-ttu-id="ce495-167">Ver todas las excepciones de número</span><span class="sxs-lookup"><span data-stu-id="ce495-167">View all number exceptions</span></span>

<span data-ttu-id="ce495-168">En este ejemplo, el **parámetro Identity** es opcional.</span><span class="sxs-lookup"><span data-stu-id="ce495-168">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="ce495-169">Si no **se especifica** el parámetro Identity, este cmdlet devuelve una lista de todos los patrones de excepción de número especificados para un inquilino.</span><span class="sxs-lookup"><span data-stu-id="ce495-169">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="ce495-170">Modificar una excepción de número</span><span class="sxs-lookup"><span data-stu-id="ce495-170">Modify a number exception</span></span>

<span data-ttu-id="ce495-171">El cmdlet **Set-CsInboundExemptNumberPattern** le permite modificar uno o varios parámetros para una identidad de patrón de número determinada.</span><span class="sxs-lookup"><span data-stu-id="ce495-171">The **Set-CsInboundExemptNumberPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span> <span data-ttu-id="ce495-172">En este ejemplo, se **requiere el** parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="ce495-172">In this example, the **Identity** parameter is required.</span></span>
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="ce495-173">Quitar una excepción de número</span><span class="sxs-lookup"><span data-stu-id="ce495-173">Remove a number exception</span></span>

<span data-ttu-id="ce495-174">El cmdlet **Remove-CsInboundExemptNumberPattern** quitará el patrón de número dado de la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="ce495-174">The **Remove-CsInboundExemptNumberPattern** cmdlet will remove the given number pattern from the tenant list.</span></span> <span data-ttu-id="ce495-175">En este ejemplo, se **requiere el** parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="ce495-175">In this example, the **Identity** parameter is required.</span></span> 

<span data-ttu-id="ce495-176">Si no se conoce la identidad, use el cmdlet **Get-CsInboundExemptNumberPattern** para localizar primero el patrón adecuado y tener en cuenta la identidad.</span><span class="sxs-lookup"><span data-stu-id="ce495-176">If the identity isn't known, use the **Get-CsInboundExemptNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="ce495-177">A continuación, ejecute el cmdlet **Remove-CsInboundExemptNumberPattern** y pase el valor de identidad adecuado.</span><span class="sxs-lookup"><span data-stu-id="ce495-177">Then, run the **Remove-CsInboundExemptNumberPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="ce495-178">Deje tiempo para la replicación antes de probar y validar.</span><span class="sxs-lookup"><span data-stu-id="ce495-178"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="ce495-179">Comprobar si un número está bloqueado</span><span class="sxs-lookup"><span data-stu-id="ce495-179">Test whether a number is blocked</span></span>

<span data-ttu-id="ce495-180">Use el cmdlet **Test-CsInboundBlockedNumberPattern** para comprobar si un número está bloqueado en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="ce495-180">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="ce495-181">El **parámetro PhoneNumber** es obligatorio y debe ser una cadena numérica sin caracteres adicionales, como +, - o ().</span><span class="sxs-lookup"><span data-stu-id="ce495-181">The **PhoneNumber** parameter is required, and should be a numeric string without any additional characters, such as +, - or ().</span></span> <span data-ttu-id="ce495-182">El parámetro **IsNumberBlocked** resultante devuelve un valor de True si el número está bloqueado en el espacio empresarial; el parámetro devuelve False si no está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="ce495-182">The resulting **IsNumberBlocked** parameter returns a value of True if the number is blocked in the tenant; the parameter returns False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a><span data-ttu-id="ce495-183">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ce495-183">Examples</span></span>

<span data-ttu-id="ce495-184">En estos ejemplos, puede ver que el número de teléfono 1 (312) 555-8884 está bloqueado, ya que debería deberse a que se encuentra en el rango bloqueado anterior, mientras que el número de teléfono 1 (312) 555-8883 puede llamar, ya que debe basarse en la exención creada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ce495-184">In these examples you can see that the phone number 1 (312) 555-8884 is blocked as it should be due to it being in the blocked range above, while the phone number 1 (312) 555-8883 is allowed to call as it should be based on the exemption created above.</span></span>

```PowerShell
Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558884

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : True
errorMessage    :

Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558883

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : False
errorMessage    :
```

## <a name="using-regex"></a><span data-ttu-id="ce495-185">Usar Regex</span><span class="sxs-lookup"><span data-stu-id="ce495-185">Using Regex</span></span>

<span data-ttu-id="ce495-186">La coincidencia de patrones para bloquear las llamadas se realiza mediante Regex.</span><span class="sxs-lookup"><span data-stu-id="ce495-186">The pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="ce495-187">Hay varias herramientas disponibles en línea para ayudar a validar una coincidencia de patrón Regex.</span><span class="sxs-lookup"><span data-stu-id="ce495-187">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="ce495-188">Si no está familiarizado con los patrones Regex, le recomendamos que dedíciese a familiarizarse con los conceptos básicos.</span><span class="sxs-lookup"><span data-stu-id="ce495-188">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="ce495-189">Para asegurarse de que obtiene los resultados esperados, use una herramienta para validar las coincidencias de patrón antes de agregar nuevas coincidencias de números bloqueados al inquilino.</span><span class="sxs-lookup"><span data-stu-id="ce495-189">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>