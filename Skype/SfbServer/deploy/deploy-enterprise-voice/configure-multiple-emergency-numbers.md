---
title: Configurar varios números de emergencia en Skype Empresarial 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 4/21/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Lea este tema para obtener información sobre cómo configurar varios números de emergencia en Skype Empresarial Server 2015.
ms.openlocfilehash: 98d9bbef92f5f3894fb288c01e474288f9f7bb4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business-2015"></a>Configurar varios números de emergencia en Skype Empresarial 2015
 
Lea este tema para obtener información sobre cómo configurar varios números de emergencia en Skype Empresarial Server 2015.
  
Skype para Business Server ahora admite varios números de emergencia para un cliente. Varios números de emergencia es una característica nueva que se introdujo en el de 2016 junio actualización acumulativa. Antes de configurar su entorno para que admita varios números de emergencia, asegúrese de leer el [Plan para varios números de emergencia en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).
  
> [!NOTE]
> Si aún no ha actualizado a la noviembre de 2016 actualización acumulativa, consulte [actualizaciones de Skype para Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). Con el noviembre de 2016 actualización acumulativa, la cantidad de números de emergencia de asistencia aumenta de 5 a 100. 
  
## <a name="configure-multiple-emergency-numbers"></a>Configurar varios números de emergencia

Para configurar varios números de emergencia, utilice el cmdlet New-CsEmergencyNumber y, a continuación, especifique el parámetro EmergencyNumbers con los cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) y [CsLocationPolicy del conjunto](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) . Para obtener una descripción completa de todos los directiva parámetros de ubicación, como el uso PSTN y ubicación requerida, consulte [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).
  
El siguiente comando crea un nuevo número de emergencia con la cadena de marcado 911 mediante el cmdlet New-CsEmergency:
  
```
> $a = New-CsEmergencyNumber -DialString 911 

```

El siguiente comando asocia el número con la directiva de ubicación indicada al especificar el parámetro EmergencyNumbers en el cmdlet Set-CsLocationPolicy:
  
```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 

```

En el siguiente ejemplo, el número de emergencia se crea con una sola máscara de marcado, 112:
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 

```

El comando siguiente crea un número de emergencia con varias máscaras de marcado:
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 

```

El siguiente ejemplo agrega varios números de emergencia con varias máscaras de marcado y, a continuación, asocia los números de emergencia con la directiva de ubicación especificada.
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 

```

El siguiente ejemplo configura varios números de emergencia de proveedores de servicios sanitarios que utilizan tanto 911 como 450:  
  
```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

El siguiente ejemplo configura varios números de emergencia de proveedores de servicios sanitarios en la ciudad de Londres:
  
```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}

```

El siguiente ejemplo configura varios números de emergencia de proveedores de servicios sanitarios en India:
  
```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}

```

El siguiente ejemplo quita una entrada existente con la cadena de marcado 911 y las máscaras de marcado 112 y 999:
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 

```


