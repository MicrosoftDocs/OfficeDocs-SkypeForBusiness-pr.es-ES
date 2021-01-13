---
title: Configurar varios números de emergencia en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Lea este tema para obtener información sobre cómo configurar varios números de emergencia en Skype Empresarial Server.
ms.openlocfilehash: fe53e914eb0c406a4f7013df2f6ec106fa781f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804110"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Configurar varios números de emergencia en Skype Empresarial

Lea este tema para obtener información sobre cómo configurar varios números de emergencia en Skype Empresarial Server.

Skype Empresarial Server ahora admite varios números de emergencia para un cliente. Varios números de emergencia es una nueva característica introducida en la actualización acumulativa de junio de 2016. Antes de configurar el entorno para admitir varios números de emergencia, asegúrese de leer Plan para varios números de emergencia [en Skype Empresarial Server.](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)

> [!NOTE]
> Si aún no ha actualizado a la actualización acumulativa de noviembre de 2016, consulte Actualizaciones de [Skype Empresarial Server 2015.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) Con la actualización acumulativa de noviembre de 2016, el número de números de emergencia de soporte técnico aumenta de 5 a 100.

## <a name="configure-multiple-emergency-numbers"></a>Configurar varios números de emergencia

Para configurar varios números de emergencia, use el cmdlet New-CsEmergencyNumber y, a continuación, especifique el parámetro EmergencyNumbers con los cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) y [Set-CsLocationPolicy.](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) Para obtener una descripción completa de todos los parámetros de directiva de ubicación, como el uso de RTC y la ubicación necesaria, consulte [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

El siguiente comando crea un nuevo número de emergencia con la cadena de marcado 911 mediante el cmdlet New-CsEmergency siguiente:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

El siguiente comando asocia el número con la directiva de ubicación especificada especificando el parámetro EmergencyNumbers en el cmdlet Set-CsLocationPolicy siguiente:

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

En el siguiente ejemplo se agregan varios números de emergencia con varias máscaras de marcado y, a continuación, se asocian los números de emergencia con la directiva de ubicación especificada:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

En el siguiente ejemplo se configuran varios números de emergencia para los proveedores de servicios de salud que usan tanto el 911 como el 450:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

En el siguiente ejemplo se configuran varios números de emergencia para la ciudad de Londres:

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

En el siguiente ejemplo se configuran varios números de emergencia para India:

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

En el siguiente ejemplo se quita una entrada existente con la cadena de marcado 911 y las máscaras de marcado 112 y 999:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
