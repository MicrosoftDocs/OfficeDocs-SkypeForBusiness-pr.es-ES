---
title: Bloquear llamadas entrantes en Skype Empresarial Online
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: dae0d585df2f67904712e9220f16213a2f925369
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238036"
---
# <a name="block-inbound-calls"></a>Bloquear llamadas entrantes

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype Empresarial Los planes de llamadas en línea ahora admiten el bloqueo de las llamadas entrantes de la red telefónica conmutada (RTC) pública. Esta característica permite definir una lista global de patrones de números de inquilino para que el identificador de llamada de todas las llamadas RTC entrantes al inquilino se pueda comprobar en la lista para obtener una coincidencia. Si se realiza una coincidencia, se rechaza una llamada entrante.

Esta característica de bloqueo de llamadas entrantes solo funciona en las llamadas entrantes que proceden de la RTC y solo funciona de forma global y empresarial. No está disponible por usuario.  

Esta característica aún no está disponible para enrutamiento directo.

>[!NOTE]
> Los autores de llamadas bloqueados pueden experimentar comportamientos ligeramente diferentes cuando se han bloqueado. El comportamiento se basa en cómo el operador del autor de la llamada bloqueado controla la notificación de que no se permite que la llamada se complete correctamente. Algunos ejemplos pueden incluir un mensaje de operador que indica que la llamada no se puede completar como marcado, o simplemente soltar la llamada.

## <a name="call-blocking-admin-controls-and-information"></a>Información y controles de administración de bloqueo de llamadas

Los controles de administración para bloquear números solo se proporcionan con PowerShell. Los patrones de bloque de números se definen como patrones de expresión regular. El orden de las expresiones no es importante: el primer patrón coincidente en la lista da como resultado que la llamada se bloquee. Un nuevo número o patrón que se agrega o quita en la lista de autores de llamadas bloqueados puede tardar hasta 24 horas en activarse.

## <a name="call-blocking-powershell-commands"></a>Comandos de PowerShell de bloqueo de llamadas

Los patrones de número se administran a través de los ```CsInboundBlockedNumberPattern``` comandos , y y ```New``` ```Get``` ```Set``` ```Remove``` . Puede administrar un patrón determinado con estos cmdlets, incluida la posibilidad de activar un patrón determinado.
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) devuelve una lista de todos los patrones de números bloqueados agregados a la lista de inquilinos, incluidos Nombre, Descripción, Habilitado (Verdadero/Falso) y Patrón para cada uno.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) agrega un patrón de número bloqueado a la lista de inquilinos.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) quita un patrón de número bloqueado de la lista de inquilinos.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o varios parámetros de un patrón de número bloqueado en la lista de inquilinos.

Ver y activar toda la característica de bloqueo de llamadas se administra a través de ```CsTenantBlockingCallingNumbers``` los comandos ```Get``` y ```Set``` .

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) devuelve los parámetros de la lista global de números bloqueados, incluido Habilitado (Verdadero/Falso). Hay una única directiva de inquilino global que no se puede modificar manualmente, aparte de activar o desactivar la característica.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar las llamadas bloqueadas de inquilino global para que se puedan desactivar y desactivar en el nivel de inquilino.

### <a name="examples"></a>Ejemplos

#### <a name="block-a-number"></a>Bloquear un número

En este ejemplo, los ```-Enabled``` parámetros y ```-Description``` son opcionales:

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

La creación de un nuevo patrón agrega el patrón como habilitado de forma predeterminada. La descripción es un campo opcional para proporcionar más información.

Le recomendamos que proporcione un nombre significativo para comprender fácilmente por qué se agregó el patrón. En el caso de bloquear simplemente los números de correo no deseado, considere la posibilidad de asignar el mismo nombre a la regla que el patrón de número que se está haciendo coincidir y agregar información adicional en la descripción según sea necesario.

Los patrones coinciden con expresiones regulares (Regex). Deje tiempo para la replicación antes de probar y validar.

#### <a name="allow-a-number"></a>Permitir un número

En este ejemplo, el ```-Identity``` parámetro es obligatorio:

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Si no se conoce la identidad, use el cmdlet para localizar primero el ```Get-CsInboundBlockedNumberPattern``` patrón adecuado y anote la identidad. Después, ejecute el ```Remove-CsTenantBlockedNumberPattern``` cmdlet y pase el valor de identidad adecuado.

Deje tiempo para la replicación antes de probar y validar.

#### <a name="view-all-number-patterns"></a>Ver todos los patrones de números

Al ejecutar este cmdlet, se devuelve una lista de todos los números bloqueados que se introducen para un inquilino:

```powershell
Get-CsInboundBlockedNumberPattern
```

Use las capacidades de filtrado de PowerShell integradas para analizar los valores devueltos según sea necesario.

## <a name="add-number-exceptions"></a>Agregar excepciones de número

Puede agregar excepciones a patrones de números bloqueados a través de los comandos ```CsTenantBlockNumberExceptionPattern``` , , y y ```New``` ```Get``` ```Set``` ```Remove``` .

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) agrega un patrón de excepción de número a la lista de inquilinos. 
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) devuelve una lista de todos los patrones de excepción de número agregados a la lista de inquilinos.
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica uno o varios parámetros en un patrón de excepción de número en la lista de inquilinos.
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) quita un patrón de excepción de número de la lista de inquilinos.

### <a name="examples"></a>Ejemplos

#### <a name="add-a-number-exception"></a>Agregar una excepción de número

En este ejemplo, se crea un nuevo patrón de excepción de número y, de forma predeterminada, se agregará el patrón como habilitado. Los ```-Enabled``` parámetros y son ```-Description``` opcionales.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Ver todas las excepciones de número

En este ejemplo, el parámetro -Identity es opcional. Si no se especifica el parámetro, este cmdlet devuelve una lista de todos los patrones de excepción de número ```-Identity``` especificados para un inquilino.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modificar una excepción de número

En este ejemplo, el parámetro -Identity es obligatorio. El ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet le permite modificar uno o varios parámetros para una identidad de patrón de número determinada.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Quitar una excepción de número

En este ejemplo, el ```-Identity``` parámetro es obligatorio. Este cmdlet quitará el patrón de número dado de la lista de inquilinos.  Si no se conoce la identidad, use el cmdlet para localizar primero el ```Get-CsInboundBlockedNumberPattern``` patrón adecuado y anote la identidad. Después, ejecute el ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet y pase el valor de identidad adecuado.Deje tiempo para la replicación antes de probar y validar.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Comprobar si un número está bloqueado

Use el ```Test-CsInboundBlockedNumberPattern``` cmdlet para comprobar si un número está bloqueado en el espacio empresarial.
 
En este ejemplo, los ```-Phonenumber``` parámetros y ```-Tenant``` son obligatorios. El ```-PhoneNumber``` parámetro debe ser una cadena numérica sin caracteres adicionales como + o -. En TRPS, el ```-Tenant parameter``` valor es opcional. El parámetro resultante devuelve un valor de Verdadero si el número está bloqueado en el espacio empresarial y ```isNumberBlocked``` Falso si no está bloqueado.

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

Como se indicó anteriormente, el patrón que coincide para bloquear las personas que llaman se realiza mediante Regex. Hay varias herramientas disponibles en línea para ayudar a validar una coincidencia de patrón Regex. Si no está familiarizado con los patrones Regex, le recomendamos que dedíciese a familiarizarse con los conceptos básicos. Para asegurarse de que obtiene los resultados esperados, use una herramienta para validar las coincidencias de patrón antes de agregar nuevas coincidencias de números bloqueados al inquilino. 

## <a name="related-topics"></a>Temas relacionados

- [Configure el equipo para administrar Skype Empresarial Online mediante Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
