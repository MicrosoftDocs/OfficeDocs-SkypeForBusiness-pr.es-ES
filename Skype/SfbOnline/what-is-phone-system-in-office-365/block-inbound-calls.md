---
title: Bloquear llamadas entrantes en Skype Empresarial Online
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
description: Los administradores pueden obtener información sobre cómo bloquear llamadas entrantes en Skype Empresarial Online.
ms.openlocfilehash: 40b43f669ededf7ac334c25c79b5af09140c075d
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671656"
---
# <a name="block-inbound-calls"></a>Bloquear llamadas entrantes

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype Empresarial planes de llamadas en línea ahora admite el bloqueo de llamadas entrantes desde la red telefónica conmutada (RTC). Esta característica permite definir una lista global de inquilinos de patrones numéricos para que el identificador de llamada de cada llamada RTC entrante al inquilino se pueda marcar en la lista para una coincidencia. Si se realiza una coincidencia, se rechazará una llamada entrante.

Esta característica de bloqueo de llamadas entrantes solo funciona en las llamadas entrantes que se originan desde la RTC y solo funciona en una base de espacio empresarial. No está disponible para cada usuario.

Esta característica aún no está disponible para enrutamiento directo.

>[!NOTE]
> Los autores de llamadas bloqueados pueden experimentar comportamientos ligeramente diferentes cuando se han bloqueado. El comportamiento se basa en la forma en que el operador del autor de la llamada bloqueado administra la notificación de que no se permite que la llamada se complete correctamente. Algunos ejemplos pueden ser un mensaje del operador que indica que la llamada no se puede completar como marcada, o simplemente dejar de llamar.

## <a name="call-blocking-admin-controls-and-information"></a>Controles e información de administración de bloqueo de llamadas

Administración controles para bloquear números se proporcionan solo con PowerShell. Los patrones de bloques numéricos se definen como patrones de expresión regular. El orden de las expresiones no es importante: el primer patrón que coincide en la lista da como resultado que la llamada se bloquee. Un nuevo número o patrón que se agrega o quita en la lista de autores de llamadas bloqueados puede tardar hasta 24 horas en activarse.

## <a name="call-blocking-powershell-commands"></a>Comandos de PowerShell de bloqueo de llamadas

Los patrones numéricos se administran mediante los ```CsInboundBlockedNumberPattern``` comandos ```New```, ```Get```, ```Set```y ```Remove```. Puede administrar un patrón determinado mediante estos cmdlets, incluida la capacidad de alternar la activación de un patrón determinado.
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) devuelve una lista de todos los patrones de número bloqueado agregados a la lista de inquilinos, incluidos Name, Description, Enabled (True/False) y Pattern para cada uno.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) agrega un patrón de número bloqueado a la lista de inquilinos.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) quita un patrón de número bloqueado de la lista de inquilinos.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o más parámetros de un patrón de número bloqueado en la lista de inquilinos.

La visualización y activación de toda la característica de bloqueo de llamadas se administra mediante los ```CsTenantBlockingCallingNumbers``` comandos ```Get``` y ```Set```.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) devuelve los parámetros para la lista global de números bloqueados, incluido Enabled (True/False). Hay una sola directiva de inquilino global que no se puede modificar manualmente excepto para activar o desactivar la característica.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permite activar y desactivar las llamadas bloqueadas del espacio empresarial global en el nivel de inquilino.

### <a name="examples"></a>Ejemplos

#### <a name="block-a-number"></a>Bloquear un número

En este ejemplo, los ```-Enabled``` parámetros y ```-Description``` son opcionales:

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

La creación de un nuevo patrón agrega el patrón como habilitado de forma predeterminada. La descripción es un campo opcional para proporcionar más información.

Le recomendamos que proporcione un nombre significativo para comprender fácilmente por qué se agregó el patrón. En el caso de simplemente bloquear los números de correo no deseado, considere asignar a la regla el mismo nombre que el patrón de número que se va a encontrar y agregue información adicional en la descripción según sea necesario.

Los patrones coinciden con las expresiones regulares (Regex).
Deje tiempo para la replicación antes de probar y validar.

#### <a name="allow-a-number"></a>Permitir un número

En este ejemplo, el ```-Identity``` parámetro es obligatorio:

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```

Si no se conoce la identidad, use el ```Get-CsInboundBlockedNumberPattern``` cmdlet para buscar primero el patrón correcto y anote la identidad. Después, ejecute el ```Remove-CsTenantBlockedNumberPattern``` cmdlet y pase el valor de identidad adecuado.

Deje tiempo para la replicación antes de probar y validar.

#### <a name="view-all-number-patterns"></a>Ver todos los patrones numéricos

La ejecución de este cmdlet devuelve una lista de todos los números bloqueados que se introducen para un espacio empresarial:

```powershell
Get-CsInboundBlockedNumberPattern
```

Use las capacidades de filtrado integradas de PowerShell para analizar los valores devueltos según sea necesario.

## <a name="add-number-exceptions"></a>Agregar excepciones de número

Puede agregar excepciones a los patrones de número bloqueados a través de los ```CsTenantBlockNumberExceptionPattern``` comandos, ```New```, ```Get```, ```Set```y ```Remove```.

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) agrega un patrón de excepción de número a la lista de inquilinos.
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) devuelve una lista de todos los patrones de excepción de número agregados a la lista de inquilinos.
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica uno o más parámetros a un patrón de excepción de número en la lista de inquilinos.
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) quita un patrón de excepción de número de la lista de inquilinos.

### <a name="examples"></a>Ejemplos

#### <a name="add-a-number-exception"></a>Agregar una excepción de número

En este ejemplo, se crea un nuevo patrón de excepción de número y, de forma predeterminada, se agrega el patrón como habilitado. Los ```-Enabled``` parámetros y ```-Description``` son opcionales.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"
```

#### <a name="view-all-number-exceptions"></a>Ver todas las excepciones de número

En este ejemplo, el parámetro -Identity es opcional. Si no se especifica el ```-Identity``` parámetro, este cmdlet devuelve una lista de todos los patrones de excepción de número especificados para un espacio empresarial.

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modificar una excepción numérica

En este ejemplo, el parámetro -Identity es obligatorio. El ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet le permite modificar uno o varios parámetros para una identidad de patrón de número determinada.

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$"
```

#### <a name="remove-a-number-exception"></a>Quitar una excepción numérica

En este ejemplo, el ```-Identity``` parámetro es obligatorio. Este cmdlet quitará el patrón de número dado de la lista de inquilinos.  Si no se conoce la identidad, use el ```Get-CsInboundBlockedNumberPattern``` cmdlet para buscar primero el patrón correcto y anote la identidad. Después, ejecute el ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet y pase el valor de identidad adecuado. Deje tiempo para la replicación antes de probar y validar.

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Comprobar si un número está bloqueado

Use el ```Test-CsInboundBlockedNumberPattern``` cmdlet para comprobar si un número está bloqueado en el inquilino.

En este ejemplo, los ```-Phonenumber``` parámetros y ```-Tenant``` son necesarios. El ```-PhoneNumber``` parámetro debe ser una cadena numérica sin caracteres adicionales, como + o -. En TRPS, el ```-Tenant parameter``` es opcional. El parámetro resultante ```isNumberBlocked``` devuelve un valor de True si el número está bloqueado en el espacio empresarial y False si no está bloqueado.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|http ResoperoCódigo  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | Verdadero        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|http ResoperoCódigo  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | Falso        |         |

## <a name="a-note-about-regex"></a>Una nota sobre Regex

Como se mencionó anteriormente, la coincidencia de patrones para bloquear a los autores de llamadas se realiza con Regex. Hay varias herramientas disponibles en línea para ayudar a validar una coincidencia de patrón de Regex. Si no está familiarizado con los patrones regex, le recomendamos que se tome algún tiempo para familiarizarse con los conceptos básicos. Para asegurarse de que obtiene los resultados esperados, use una herramienta para validar las coincidencias de patrón antes de agregar nuevas coincidencias de número bloqueado a su inquilino.

## <a name="related-topics"></a>Temas relacionados

- [Configurar el equipo para administrar Skype Empresarial Online con Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
