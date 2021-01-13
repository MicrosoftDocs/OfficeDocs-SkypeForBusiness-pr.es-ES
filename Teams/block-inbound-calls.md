---
title: Bloquear las llamadas entrantes en Microsoft Teams
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
ms.openlocfilehash: ca2f8de5962572a08ab2a0ae7127446d14334c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799910"
---
# <a name="block-inbound-calls"></a>Bloquear llamadas entrantes

Los planes de enrutamiento directo y llamadas de sistema telefónico admiten el bloqueo de llamadas entrantes de la red telefónica conmutada (RTC). Esta característica permite definir una lista global de inquilinos de patrones de números para que el identificador de llamada de cada llamada RTC entrante al inquilino se pueda comprobar en la lista para obtener una coincidencia. Si se realiza una coincidencia, se rechazará una llamada entrante.

Esta característica de bloqueo de llamadas entrantes solo funciona en llamadas entrantes procedentes de RTC y solo funciona de forma global del inquilino. No está disponible para cada usuario.  

>[!NOTE]
> Los autores de llamadas bloqueados pueden experimentar comportamientos ligeramente diferentes cuando se han bloqueado. El comportamiento se basa en cómo el operador del autor de la llamada bloqueado controla la notificación de que no se permite que la llamada se complete correctamente. Algunos ejemplos pueden ser un mensaje del operador en el que se indica que la llamada no se puede completar como marcado, o simplemente dejar de recibir la llamada.

## <a name="call-blocking-admin-controls-and-information"></a>Información y controles de administración de bloqueo de llamadas

Los controles de administración para bloquear números solo se proporcionan con PowerShell. Los patrones de bloques de números se definen como patrones de expresiones regulares. El orden de las expresiones no es importante: el primer patrón coincide en la lista y la llamada se bloquea. Un nuevo número o patrón que se agrega o se quita en la lista de autores de llamadas bloqueados puede tardar hasta 24 horas en activarse en el patrón.

## <a name="call-blocking-powershell-commands"></a>Comandos de PowerShell de bloqueo de llamadas

Para administrar los patrones de números, use los cmdlets **New,** **Get,** **Set** y **Remove**  - **CsInboundBlockedNumberPattern.** Puede administrar un patrón determinado usando estos cmdlets, incluida la capacidad de activar un patrón determinado.

- [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) devuelve una lista de todos los patrones de números bloqueados agregados a la lista de inquilinos, incluidos Nombre, Descripción, Habilitado (Verdadero/Falso) y Patrón para cada uno de ellos.
- [New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) agrega un patrón de números bloqueados a la lista de inquilinos.
- [Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) quita un patrón de números bloqueados de la lista de inquilinos.
- [Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifica uno o varios parámetros de un patrón de número bloqueado en la lista de inquilinos.

La visualización y activación de toda la característica de bloqueo de llamadas se administra mediante los cmdlets **Get**, **Set**  - **CsTenantBlockingCallingNumbers.**

- [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) devuelve los parámetros para la lista de números bloqueados global, incluido Enabled (True/False). Hay una sola directiva de inquilino global que no se puede modificar manualmente, aparte de activar o desactivar la característica.
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar el inquilino global de llamadas bloqueadas que se deben activado y desactivado en el nivel de inquilino.

### <a name="examples"></a>Ejemplos

#### <a name="block-a-number"></a>Bloquear un número

En este ejemplo, los **parámetros Habilitado** y **Descripción** son opcionales.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

Al crear un nuevo patrón se agrega el patrón como habilitado de forma predeterminada. La descripción es un campo opcional para proporcionar más información.

Le recomendamos que proporcione un nombre significativo para comprender fácilmente por qué se agregó el patrón. En el caso de bloquear simplemente números de correo no deseado, considere la posibilidad de asignar a la regla el mismo nombre que el patrón de números que coincide y agregar información adicional en la descripción según sea necesario.

Los patrones coinciden mediante expresiones regulares (Regex). Deje tiempo para la replicación antes de probar y validar.

#### <a name="allow-a-number"></a>Permitir un número

En este ejemplo, se **requiere el** parámetro Identity.

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Si no se conoce la identidad, use el cmdlet **Get-CsInboundBlockedNumberPattern** para buscar primero el patrón adecuado y anote la identidad. Después, ejecute el **cmdlet Remove-CsTenantBlockedNumberPattern** y pase el valor de identidad adecuado.

Deje tiempo para la replicación antes de probar y validar.

#### <a name="view-all-number-patterns"></a>Ver todos los patrones de números

Al ejecutar este cmdlet, se devuelve una lista de todos los números bloqueados que se introducen para un inquilino:

```powershell
Get-CsInboundBlockedNumberPattern
```

Use las capacidades de filtrado de PowerShell integradas para analizar los valores devueltos según sea necesario.

## <a name="add-number-exceptions"></a>Agregar excepciones de número

Puede agregar excepciones a los patrones de números bloqueados mediante los cmdlets **New**, **Get,** **Set**, **Remove**  - **CsTenantBlockNumberExceptionPattern.**

- [New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) agrega un patrón de excepciones de número a la lista de inquilinos. 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) devuelve una lista de todos los patrones de excepciones de número agregados a la lista de inquilinos.
- [Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica uno o más parámetros para un patrón de excepción de número en la lista de inquilinos.
- [Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) quita un patrón de excepciones de número de la lista de inquilinos.

### <a name="examples"></a>Ejemplos

#### <a name="add-a-number-exception"></a>Agregar una excepción de número

En este ejemplo, se crea un nuevo patrón de excepciones de número y, de forma predeterminada, agregará el patrón como habilitado. Los **parámetros Habilitado** y **Descripción** son opcionales.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Ver todas las excepciones de número

En este ejemplo, el **parámetro Identity** es opcional. Si no se especifica el parámetro **Identity,** este cmdlet devuelve una lista de todos los patrones de excepciones de número especificados para un espacio empresarial.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modificar una excepción de número

En este ejemplo, el **parámetro Identity** es obligatorio. El cmdlet **Set-CsTenantBlockedNumberExceptionPattern** le permite modificar uno o varios parámetros para una identidad de patrón de número determinada.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Quitar una excepción de número

En este ejemplo, se **requiere el** parámetro Identity. Este cmdlet quitará el patrón de números dado de la lista de inquilinos.  Si no se conoce la identidad, use el cmdlet **Get-CsInboundBlockedNumberPattern** para buscar primero el patrón adecuado y anote la identidad. Después, ejecute el cmdlet **Remove-CsTenantBlockedNumberExceptionPattern** y pase el valor de identidad adecuado.Deje tiempo para la replicación antes de probar y validar.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Comprobar si un número está bloqueado

Use el **cmdlet Test-CsInboundBlockedNumberPattern** para comprobar si un número está bloqueado en el espacio empresarial.
 
En este ejemplo, son **necesarios los parámetros PhoneNumber** y **Tenant.** El **parámetro PhoneNumber** debe ser una cadena numérica sin ningún carácter adicional, como + o -. En PVS, el **parámetro tenant** es opcional. El parámetro **isNumberBlocked** resultante devuelve un valor True si el número está bloqueado en el espacio empresarial y False si no está bloqueado.

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

Como se ha mencionado anteriormente, el patrón de coincidencia para bloquear autores de llamadas se realiza mediante Regex. Hay disponibles varias herramientas en línea para ayudar a validar la coincidencia de un patrón Regex. Si no está familiarizado con los patrones Regex, le recomendamos que se tome algún tiempo para familiarizarse con los conceptos básicos. Para asegurarse de que obtiene los resultados esperados, use una herramienta para validar coincidencias de patrones antes de agregar nuevas coincidencias de número bloqueados al inquilino.
