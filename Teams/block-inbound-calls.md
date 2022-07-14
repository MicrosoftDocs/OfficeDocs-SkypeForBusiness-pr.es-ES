---
title: Bloquear llamadas entrantes en Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
ms.custom: ''
description: Obtenga información sobre cómo usar PowerShell para administrar el bloqueo de llamadas entrantes.
ms.openlocfilehash: 217a4fe6770d916e9013acf7f90ebf6a5556b837
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789605"
---
# <a name="block-inbound-calls"></a>Bloquear llamadas entrantes

Planes de llamadas de Microsoft, enrutamiento directo y operador Conectar todo el soporte técnico que bloquea las llamadas entrantes desde la red telefónica conmutada (RTC). Esta característica permite a un administrador definir una lista de patrones de número en el nivel global del inquilino para que el identificador de llamada de cada llamada RTC entrante al inquilino se pueda comprobar en la lista para obtener una coincidencia. Si se realiza una coincidencia, se rechazará una llamada entrante.

Esta característica de bloqueo de llamadas entrantes solo funciona en las llamadas entrantes que se originan desde rtc y solo funciona en un nivel global de inquilino. Los usuarios individuales de Teams no pueden manipular esta lista. El cliente de Teams permite que los usuarios individuales bloqueen las llamadas RTC. Para obtener información sobre cómo los usuarios finales pueden implementar el bloqueo de llamadas, consulte [Administrar la configuración de llamadas en Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).

> [!NOTE]
> Los autores de llamadas bloqueados pueden experimentar comportamientos ligeramente diferentes cuando se bloquean. El comportamiento se basa en la forma en que el operador del autor de la llamada bloqueado administra la notificación de que no se permite que la llamada se complete correctamente. Algunos ejemplos pueden ser un mensaje del operador que indica que la llamada no se puede completar como marcada, o simplemente dejar de llamar.

## <a name="call-blocking-admin-controls-and-information"></a>Controles e información de administración de bloqueo de llamadas

Administración controles para bloquear números se proporcionan solo con PowerShell. Los patrones de bloques numéricos se definen como patrones de expresión regular. El orden de las expresiones no es importante: el primer patrón que coincide en la lista da como resultado que la llamada se bloquee. Un nuevo número o patrón que se agrega o quita en la lista de autores de llamadas bloqueados puede tardar hasta 24 horas en activarse.

## <a name="call-blocking-powershell-commands"></a>Comandos de PowerShell de bloqueo de llamadas

Los patrones numéricos se administran mediante los cmdlets **New-**, **Get-**, **Set-y** **Remove-CsInboundBlockedNumberPattern** . Puede administrar un patrón determinado mediante estos cmdlets, incluida la capacidad de alternar la activación de un patrón determinado.

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) devuelve una lista de todos los patrones de número bloqueado agregados a la lista de inquilinos, incluidos Name, Description, Enabled (True/False) y Pattern para cada uno.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) agrega un patrón de número bloqueado a la lista de inquilinos.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) quita un patrón de número bloqueado de la lista de inquilinos.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o más parámetros de un patrón de número bloqueado en la lista de inquilinos.

La visualización y activación de toda la característica de bloqueo de llamadas se administra mediante los cmdlets **Get** y **Set-CsTenantBlockingCallingNumbers** .

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) devuelve los patrones de número de bloque de entrada y los parámetros de patrones de número de número de entrada exentos para la lista global de números bloqueados. Este cmdlet también devuelve si el bloqueo se ha habilitado (True o False). Hay una sola directiva de inquilino global que no se puede modificar manualmente excepto para activar o desactivar la característica.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permite activar y desactivar las llamadas bloqueadas del espacio empresarial global en el nivel de inquilino.

### <a name="examples"></a>Ejemplos

#### <a name="block-a-number"></a>Bloquear un número

En el ejemplo siguiente, el administrador de inquilinos quiere bloquear todas las llamadas procedentes del intervalo de números 1 (312) 555-0000 a 1 (312) 555-9999. El patrón de números se crea de modo que coincidan los números del rango con + con prefijo y los números del rango sin + con prefijo. No es necesario incluir los símbolos – y () en los números de teléfono porque el sistema los quita antes de hacer coincidir.  Para activar el patrón de número, el parámetro **Enabled** se establece en True. Para deshabilitar este patrón de número específico, establezca el parámetro en False.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

En el siguiente ejemplo, el administrador de inquilinos quiere bloquear todas las llamadas procedentes del número 1 (412) 555-1234. Para activar el patrón de número, el parámetro **Enabled** se establece en True.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

La creación de un nuevo patrón agrega el patrón como habilitado de forma predeterminada. La descripción es un campo opcional para proporcionar más información.

Le recomendamos que proporcione un nombre significativo para comprender fácilmente por qué se agregó el patrón. En el caso de simplemente bloquear los números de correo no deseado, considere asignar a la regla el mismo nombre que el patrón de número que se va a encontrar y agregue información adicional en la descripción según sea necesario.

Los patrones coinciden con las expresiones regulares (Regex). Para obtener más información, consulte [Uso de Regex](#using-regex).

Deje tiempo para la replicación antes de probar y validar.

#### <a name="allow-a-number"></a>Permitir un número

Puede permitir que un número llame quitando el patrón de número bloqueado. En el ejemplo siguiente, el administrador de inquilinos quiere permitir que 1 (412) 555-1234 realice llamadas de nuevo.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```

Si no se conoce la identidad, use el cmdlet **Get-CsInboundBlockedNumberPattern** para buscar primero el patrón correcto y anote la identidad. A continuación, ejecute el cmdlet **Remove-CsInboundBlockedNumberPattern** y pase el valor de identidad adecuado.

Deje tiempo para la replicación antes de probar y validar.

#### <a name="view-all-number-patterns"></a>Ver todos los patrones numéricos

La ejecución de este cmdlet devuelve una lista de todos los números bloqueados que se introducen para un espacio empresarial:

```powershell
Get-CsInboundBlockedNumberPattern
```

Use las capacidades de filtrado integradas de PowerShell para analizar los valores devueltos según sea necesario.

## <a name="add-number-exceptions"></a>Agregar excepciones de número

Puede agregar excepciones a los patrones de número bloqueado mediante los cmdlets **New-**, **Get-**, **Set-y** **Remove-CsInboundExemptNumberPattern** .

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) agrega un patrón de excepción de número a la lista de inquilinos.
- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) devuelve una lista de todos los patrones de excepción de número agregados a la lista de inquilinos.
- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifica uno o más parámetros a un patrón de excepción de número en la lista de inquilinos.
- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) quita un patrón de excepción de número de la lista de inquilinos.

### <a name="examples"></a>Ejemplos

#### <a name="add-a-number-exception"></a>Agregar una excepción de número

En el ejemplo siguiente, el administrador de inquilinos quiere permitir que los números de teléfono 1 (312) 555-8882 y 1 (312) 555-8883 realicen llamadas al inquilino, incluso si estos dos números de teléfono están en el intervalo que se ha bloqueado en el ejemplo anterior. Para habilitar esto, se crea un nuevo patrón de excepción de número de la siguiente manera:

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

Para activar el patrón de número, el parámetro **Enabled** se establece en True. Para deshabilitar este patrón de número específico, establezca el parámetro en False.

#### <a name="view-all-number-exceptions"></a>Ver todas las excepciones de número

En este ejemplo, el parámetro **Identity** es opcional. Si no se especifica el parámetro **Identity** , este cmdlet devuelve una lista de todos los patrones de excepción de número especificados para un espacio empresarial.

```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Get-CsInboundExemptNumberPattern
```

#### <a name="modify-a-number-exception"></a>Modificar una excepción numérica

El cmdlet **Set-CsInboundExemptNumberPattern** le permite modificar uno o más parámetros para una identidad de patrón de número determinada. En este ejemplo, el parámetro **Identity** es obligatorio.

```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>Quitar una excepción numérica

El cmdlet **Remove-CsInboundExemptNumberPattern** quitará el patrón de número determinado de la lista de inquilinos. En este ejemplo, el parámetro **Identity** es obligatorio.

Si no se conoce la identidad, use el cmdlet **Get-CsInboundExemptNumberPattern** para buscar primero el patrón correcto y anote la identidad. Después, ejecute el cmdlet **Remove-CsInboundExemptNumberPattern** y pase el valor de identidad adecuado. Deje tiempo para la replicación antes de probar y validar.

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>Comprobar si un número está bloqueado

Use el cmdlet **Test-CsInboundBlockedNumberPattern** para comprobar si un número está bloqueado en el espacio empresarial.

El parámetro **PhoneNumber** es obligatorio y debe ser una cadena numérica sin caracteres adicionales, como +, - o (). El parámetro **IsNumberBlocked** resultante devuelve un valor de True si el número está bloqueado en el espacio empresarial; el parámetro devuelve False si no está bloqueado.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>Ejemplos

En estos ejemplos puede ver que el número de teléfono 1 (312) 555-8884 está bloqueado, ya que debería debe deberse a que se encuentra en el rango bloqueado anterior, mientras que el número de teléfono 1 (312) 555-8883 se permite llamar, ya que debería basarse en la exención creada anteriormente.

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

## <a name="using-regex"></a>Uso de Regex

La coincidencia de patrones para bloquear a los autores de llamadas se realiza con Regex. Hay varias herramientas disponibles en línea para ayudar a validar una coincidencia de patrón de Regex. Si no está familiarizado con los patrones regex, le recomendamos que se tome algún tiempo para familiarizarse con los conceptos básicos. Para asegurarse de que obtiene los resultados esperados, use una herramienta para validar las coincidencias de patrón antes de agregar nuevas coincidencias de número bloqueado a su inquilino.
