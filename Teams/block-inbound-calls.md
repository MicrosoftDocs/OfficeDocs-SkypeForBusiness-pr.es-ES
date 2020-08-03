---
title: Bloquear llamadas entrantes en Microsoft Teams
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 3bb1222f0662228e5c0de7b2253cbac162571b1e
ms.sourcegitcommit: a36514c7c8ea47bde4edb09c11ff99061b1f74c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094686"
---
# <a name="block-inbound-calls"></a>Bloquear llamadas entrantes

Los planes de llamadas y enrutamiento directo del sistema telefónico admiten el bloqueo de llamadas entrantes desde la red de telefonía pública conmutada (RTC). Esta característica permite que se defina una lista global de inquilinos de patrones de números para que la identificación de llamadas de todas las llamadas RTC entrantes en el inquilino se pueda comprobar con la lista en busca de una coincidencia. Si se realiza una coincidencia, se rechaza una llamada entrante.

Esta característica de bloqueo de llamadas entrantes solo funciona en llamadas entrantes que se originan desde la RTC y solo funciona con un inquilino global. No está disponible para cada usuario.  

>[!NOTE]
> Los autores de llamadas bloqueados pueden experimentar comportamientos ligeramente diferentes cuando se han bloqueado. El comportamiento se basa en la forma en que el portador de la persona que llama bloqueada controla la notificación de que la llamada no se puede completar correctamente. Es posible que algunos ejemplos incluyan un mensaje que indica que la llamada no se puede completar como marcando o simplemente se encuentra en la llamada.

## <a name="call-blocking-admin-controls-and-information"></a>Información y controles de administración con bloqueo de llamadas

Los controles de administración para números de bloqueo se proporcionan con PowerShell solo. Los patrones de bloques de números se definen como patrones de expresiones regulares. El orden de las expresiones no es importante, el primer patrón que coincide en la lista provoca la bloqueo de la llamada. Un nuevo número o patrón que se agrega o se elimina en la lista de llamadas bloqueadas puede demorar hasta 24 horas para que el patrón se active.

## <a name="call-blocking-powershell-commands"></a>Comandos de PowerShell de bloqueo de llamadas

Para administrar los patrones de números, use los cmdlets **New**, **Get**, **set**, **Remove**  - **CsInboundBlockedNumberPattern** . Puede administrar un patrón determinado con estos cmdlets, incluida la capacidad de activar o desactivar la activación de un patrón determinado.

- [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) devuelve una lista de todos los patrones de números bloqueados agregados a la lista de inquilinos, como nombre, descripción, habilitado (verdadero/falso) y patrón para cada uno.
- [New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) agrega un patrón de números bloqueados a la lista de inquilinos.
- [Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) quita un patrón de números bloqueados de la lista de inquilinos.
- [Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o más parámetros de un patrón de número bloqueado en la lista de inquilinos.

La visualización y activación de toda la característica de bloqueo de llamadas se administra a través de los cmdlets **Get**, **set**  - **CsTenantBlockingCallingNumbers** .

- [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) devuelve los parámetros de la lista global de números bloqueados, que incluye Enabled (verdadero/falso). Hay una única directiva de inquilino global que no se puede modificar de forma manual salvo para activar o desactivar la característica.
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar las llamadas de inquilino global bloqueadas y desactivadas en el nivel de inquilino.

### <a name="examples"></a>Ejemplos

#### <a name="block-a-number"></a>Bloquear un número

En este ejemplo, los parámetros **Enabled** y **Description** son opcionales.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

La creación de un nuevo patrón agrega el patrón como habilitado de forma predeterminada. La descripción es un campo opcional para proporcionar más información.

Le recomendamos que proporcione un nombre significativo para comprender fácilmente por qué se agregó el patrón. En el caso de simplemente bloquear los números de correo no deseado, considere la posibilidad de nombrar la regla como el patrón de número que se está cotejando y agregue información adicional en la descripción según sea necesario.

Los patrones coinciden con expresiones regulares (regex). Deje tiempo para la replicación antes de probar y validar.

#### <a name="allow-a-number"></a>Permitir un número

En este ejemplo, se requiere el parámetro **Identity** .

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Si no se conoce la identidad, use el cmdlet **Get-CsInboundBlockedNumberPattern** para ubicar primero el patrón adecuado y anote la identidad. A continuación, ejecute el cmdlet **Remove-CsTenantBlockedNumberPattern** y pase el valor de identidad adecuado.

Deje tiempo para la replicación antes de probar y validar.

#### <a name="view-all-number-patterns"></a>Ver todos los patrones de números

La ejecución de este cmdlet devuelve una lista de todos los números bloqueados que se especifican para un inquilino:

```powershell
Get-CsInboundBlockedNumberPattern
```

Use las capacidades de filtrado de PowerShell integradas para analizar los valores devueltos según sea necesario.

## <a name="add-number-exceptions"></a>Agregar excepciones de número

Puede Agregar excepciones a patrones de números bloqueados con los cmdlets **New**, **Get**, **set**, **Remove**  - **CsTenantBlockNumberExceptionPattern** .

- [New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) agrega un patrón de excepción de número a la lista de inquilinos. 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) devuelve una lista de todos los patrones de excepción de los números agregados a la lista de inquilinos.
- [Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica uno o más parámetros a un patrón de excepción de número en la lista de inquilinos.
- [Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) quita un patrón de excepción de número de la lista de inquilinos.

### <a name="examples"></a>Ejemplos

#### <a name="add-a-number-exception"></a>Agregar una excepción de número

En este ejemplo, se crea un patrón de excepción de número nuevo y, de forma predeterminada, agregará el patrón como habilitado. Los parámetros **Enabled** y **Description** son opcionales.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Ver todas las excepciones de números

En este ejemplo, el parámetro **Identity** es opcional. Si no se especifica el parámetro **Identity** , este cmdlet devuelve una lista de todos los patrones de excepción de número especificados para un inquilino.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modificar una excepción de número

En este ejemplo, el parámetro **Identity** es obligatorio. El cmdlet **set-CsTenantBlockedNumberExceptionPattern** le permite modificar uno o más parámetros para una identidad de patrón de número determinada.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Quitar una excepción de número

En este ejemplo, se requiere el parámetro **Identity** . Este cmdlet quitará el patrón de número dado de la lista de inquilinos.  Si no se conoce la identidad, use el cmdlet **Get-CsInboundBlockedNumberPattern** para ubicar primero el patrón adecuado y anote la identidad. A continuación, ejecute el cmdlet **Remove-CsTenantBlockedNumberExceptionPattern** y pase el valor de identidad adecuado.Deje tiempo para la replicación antes de probar y validar.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Comprobar si un número está bloqueado

Use el cmdlet **Test-CsInboundBlockedNumberPattern** para comprobar si un número está bloqueado en el inquilino.
 
En este ejemplo, los parámetros **PhoneNumber** y **tenant** son obligatorios. El parámetro **PhoneNumber** debe ser una cadena numérica sin caracteres adicionales, como + o-. En TRPS, el **parámetro tenant** es opcional. El parámetro **isNumberBlocked** resultante devuelve el valor true si el número está bloqueado en el inquilino y false si no está bloqueado.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | Verdadero        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | Falso        |         |

## <a name="a-note-about-regex"></a>Una nota sobre Regex

Como se indicó anteriormente, la coincidencia de patrones para las personas que llaman se realiza usando Regex. Hay varias herramientas disponibles en línea para ayudar a validar una coincidencia de patrón de Regex. Si no está familiarizado con los patrones de Regex, le recomendamos que tome algún tiempo para familiarizarse con los conceptos básicos. Para asegurarse de que obtiene los resultados esperados, use una herramienta para validar las coincidencias de modelos antes de agregar nuevas coincidencias de número bloqueado a su espacio empresarial.