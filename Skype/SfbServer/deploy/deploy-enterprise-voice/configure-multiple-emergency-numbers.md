---
title: Configurar varios números de emergencia en Skype empresarial
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Lea este tema para obtener información sobre cómo configurar varios números de emergencia en Skype empresarial Server.
ms.openlocfilehash: 81d3dbed919c936eb8a656d123f5c44e445044d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027801"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Configurar varios números de emergencia en Skype empresarial

Lea este tema para obtener información sobre cómo configurar varios números de emergencia en Skype empresarial Server.

Skype empresarial Server ahora admite varios números de emergencia para un cliente. Varios números de emergencia son una nueva característica que se presenta en la actualización acumulativa de junio de 2016. Antes de configurar el entorno para que admita varios números de emergencia, asegúrese de leer [plan de varios números de emergencia en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).

> [!NOTE]
> Si aún no ha actualizado a la actualización acumulativa de noviembre de 2016, consulte [actualizaciones para Skype empresarial Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). Con la actualización acumulativa de noviembre de 2016, el número de números de emergencia de soporte aumenta de 5 a 100.

## <a name="configure-multiple-emergency-numbers"></a>Configurar varios números de emergencia

Para configurar varios números de emergencia, use el cmdlet New-CsEmergencyNumber y, a continuación, especifique el parámetro EmergencyNumbers con los cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) y [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) . Para obtener una descripción completa de todos los parámetros de la Directiva de ubicación, como uso de RTC y ubicación necesaria, consulte [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

El siguiente comando crea un nuevo número de emergencia con la cadena de marcado 911 mediante el cmdlet New-CsEmergency:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

El comando siguiente asocia el número con la Directiva de ubicación especificada especificando el parámetro EmergencyNumbers en el cmdlet Set-CsLocationPolicy:

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

En el siguiente ejemplo, se crea un número de emergencia con una sola máscara de marcado, 112:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

El siguiente comando crea un número de emergencia con varias máscaras de marcado:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

En el siguiente ejemplo se agregan varios números de emergencia con varias máscaras de marcado y, a continuación, se asocian los números de emergencia con la Directiva de ubicación especificada:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

El siguiente ejemplo configura varios números de emergencia para proveedores de servicios de salud que usan tanto 911 como 450:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

El siguiente ejemplo configura varios números de emergencia para la ciudad de Londres:

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

El siguiente ejemplo configura varios números de emergencia para la India:

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

El siguiente ejemplo quita una entrada existente con la cadena de marcado 911 y las máscaras de marcado 112 y 999:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
