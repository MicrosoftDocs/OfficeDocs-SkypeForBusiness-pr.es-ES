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
# <a name="block-inbound-calls"></a>Bloquear llamadas entrantes

Los planes de llamadas de Microsoft, el enrutamiento directo y el operador Conectar todas las llamadas entrantes de la red telefónica conmutada (RTC) pública. Esta característica permite a un administrador definir una lista de patrones de número en el nivel global del inquilino para que el identificador de llamada de todas las llamadas RTC entrantes al inquilino se pueda comprobar en la lista para obtener una coincidencia. Si se realiza una coincidencia, se rechaza una llamada entrante.

Esta característica de bloqueo de llamadas entrantes solo funciona en las llamadas entrantes que proceden de la RTC y solo funciona en un nivel global de inquilino. Los Teams usuarios no pueden manipular esta lista. El Teams permite a los usuarios individuales bloquear llamadas RTC. Para obtener información sobre cómo los usuarios finales pueden implementar el bloqueo de llamadas, vea Administrar la configuración de llamadas [en Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).

>[!NOTE]
> Los autores de llamadas bloqueados pueden experimentar comportamientos ligeramente diferentes cuando se han bloqueado. El comportamiento se basa en cómo el operador del autor de la llamada bloqueado controla la notificación de que no se permite que la llamada se complete correctamente. Algunos ejemplos pueden incluir un mensaje de operador que indica que la llamada no se puede completar como marcado, o simplemente soltar la llamada.

## <a name="call-blocking-admin-controls-and-information"></a>Información y controles de administración de bloqueo de llamadas

Los controles de administración para bloquear números solo se proporcionan con PowerShell. Los patrones de bloque de números se definen como patrones de expresión regular. El orden de las expresiones no es importante: el primer patrón coincidente en la lista da como resultado que la llamada se bloquee. Un nuevo número o patrón que se agrega o quita en la lista de autores de llamadas bloqueados puede tardar hasta 24 horas en activarse.

## <a name="call-blocking-powershell-commands"></a>Comandos de PowerShell de bloqueo de llamadas

Los patrones de número se administran con los cmdlets **New-**, **Get-**, **Set-** y **Remove-CsInboundBlockedNumberPattern.** Puede administrar un patrón determinado con estos cmdlets, incluida la posibilidad de activar un patrón determinado.

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) devuelve una lista de todos los patrones de números bloqueados agregados a la lista de inquilinos, incluidos Nombre, Descripción, Habilitado (Verdadero/Falso) y Patrón para cada uno.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) agrega un patrón de número bloqueado a la lista de inquilinos.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) quita un patrón de número bloqueado de la lista de inquilinos.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o varios parámetros de un patrón de número bloqueado en la lista de inquilinos.

Ver y activar toda la característica de bloqueo de llamadas se administra a través de los cmdlets **Get y** **Set-CsTenantBlockingCallingNumbers.**

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) devuelve los patrones de número de bloque de entrada y los parámetros de patrones de números exentos de entrada para la lista global de números bloqueados. Este cmdlet también devuelve si el bloqueo se ha habilitado (Verdadero o Falso). Hay una única directiva de inquilino global que no se puede modificar manualmente, aparte de activar o desactivar la característica.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar las llamadas bloqueadas de inquilino global para que se puedan desactivar y desactivar en el nivel de inquilino.

### <a name="examples"></a>Ejemplos

#### <a name="block-a-number"></a>Bloquear un número

En el siguiente ejemplo, el administrador de inquilinos quiere bloquear todas las llamadas procedentes del rango de números 1 (312) 555-0000 a 1 (312) 555-9999. Se crea el patrón de números para que ambos números del rango con + prefijo y los números del rango sin + prefijo coincidan. No es necesario incluir los símbolos y () en los números de teléfono porque el sistema los quita antes de hacer coincidir.  Para activar el patrón de números, el **parámetro Enabled** se establece en True. Para deshabilitar este patrón de número específico, establezca el parámetro en Falso.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

En el siguiente ejemplo, el administrador de inquilinos quiere bloquear todas las llamadas procedentes del número 1 (412) 555-1234. Para activar el patrón de números, el **parámetro Enabled** se establece en True.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

La creación de un nuevo patrón agrega el patrón como habilitado de forma predeterminada. La descripción es un campo opcional para proporcionar más información.

Le recomendamos que proporcione un nombre significativo para comprender fácilmente por qué se agregó el patrón. En el caso de bloquear simplemente los números de correo no deseado, considere la posibilidad de asignar el mismo nombre a la regla que el patrón de número que se está haciendo coincidir y agregar información adicional en la descripción según sea necesario.

Los patrones coinciden con expresiones regulares (Regex). Para obtener más información, vea [Usar Regex](#using-regex).

Deje tiempo para la replicación antes de probar y validar. 

#### <a name="allow-a-number"></a>Permitir un número

Puede permitir que un número llame quitando el patrón de número bloqueado. En el siguiente ejemplo, el administrador de inquilinos quiere permitir que 1 (412) 555-1234 vuelva a realizar llamadas.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
Si no se conoce la identidad, use el cmdlet **Get-CsInboundBlockedNumberPattern** para localizar primero el patrón adecuado y anote la identidad. Después, ejecute el cmdlet **Remove-CsInboundBlockedNumberPattern** y pase el valor de identidad adecuado.

Deje tiempo para la replicación antes de probar y validar.

#### <a name="view-all-number-patterns"></a>Ver todos los patrones de números

Al ejecutar este cmdlet, se devuelve una lista de todos los números bloqueados que se introducen para un inquilino:

```powershell
Get-CsInboundBlockedNumberPattern
```

Use las capacidades de filtrado de PowerShell integradas para analizar los valores devueltos según sea necesario.

## <a name="add-number-exceptions"></a>Agregar excepciones de número

Puede agregar excepciones a los patrones de números bloqueados mediante los cmdlets **New-**, **Get-**, **Set-** y **Remove-CsInboundExemptNumberPattern.**

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) agrega un patrón de excepción de número a la lista de inquilinos. 
- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) devuelve una lista de todos los patrones de excepción de número agregados a la lista de inquilinos.
- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifica uno o varios parámetros en un patrón de excepción de número en la lista de inquilinos.
- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) quita un patrón de excepción de número de la lista de inquilinos.

### <a name="examples"></a>Ejemplos

#### <a name="add-a-number-exception"></a>Agregar una excepción de número

En el ejemplo siguiente, el administrador de inquilinos desea permitir que los números de teléfono 1 (312) 555-8882 y 1 (312) 555-8883 realicen llamadas al inquilino, incluso si estos dos números de teléfono están en el rango que se ha bloqueado en el ejemplo anterior. Para habilitar esta opción, se crea un nuevo patrón de excepción de número de la siguiente manera:

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

Para activar el patrón de números, el **parámetro Enabled** se establece en True. Para deshabilitar este patrón de número específico, establezca el parámetro en Falso.


#### <a name="view-all-number-exceptions"></a>Ver todas las excepciones de número

En este ejemplo, el **parámetro Identity** es opcional. Si no **se especifica** el parámetro Identity, este cmdlet devuelve una lista de todos los patrones de excepción de número especificados para un inquilino.
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a>Modificar una excepción de número

El cmdlet **Set-CsInboundExemptNumberPattern** le permite modificar uno o varios parámetros para una identidad de patrón de número determinada. En este ejemplo, se **requiere el** parámetro Identity.
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>Quitar una excepción de número

El cmdlet **Remove-CsInboundExemptNumberPattern** quitará el patrón de número dado de la lista de inquilinos. En este ejemplo, se **requiere el** parámetro Identity. 

Si no se conoce la identidad, use el cmdlet **Get-CsInboundExemptNumberPattern** para localizar primero el patrón adecuado y tener en cuenta la identidad. A continuación, ejecute el cmdlet **Remove-CsInboundExemptNumberPattern** y pase el valor de identidad adecuado.Deje tiempo para la replicación antes de probar y validar.  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>Comprobar si un número está bloqueado

Use el cmdlet **Test-CsInboundBlockedNumberPattern** para comprobar si un número está bloqueado en el espacio empresarial.
 
El **parámetro PhoneNumber** es obligatorio y debe ser una cadena numérica sin caracteres adicionales, como +, - o (). El parámetro **IsNumberBlocked** resultante devuelve un valor de True si el número está bloqueado en el espacio empresarial; el parámetro devuelve False si no está bloqueado.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>Ejemplos

En estos ejemplos, puede ver que el número de teléfono 1 (312) 555-8884 está bloqueado, ya que debería deberse a que se encuentra en el rango bloqueado anterior, mientras que el número de teléfono 1 (312) 555-8883 puede llamar, ya que debe basarse en la exención creada anteriormente.

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

## <a name="using-regex"></a>Usar Regex

La coincidencia de patrones para bloquear las llamadas se realiza mediante Regex. Hay varias herramientas disponibles en línea para ayudar a validar una coincidencia de patrón Regex. Si no está familiarizado con los patrones Regex, le recomendamos que dedíciese a familiarizarse con los conceptos básicos. Para asegurarse de que obtiene los resultados esperados, use una herramienta para validar las coincidencias de patrón antes de agregar nuevas coincidencias de números bloqueados al inquilino.