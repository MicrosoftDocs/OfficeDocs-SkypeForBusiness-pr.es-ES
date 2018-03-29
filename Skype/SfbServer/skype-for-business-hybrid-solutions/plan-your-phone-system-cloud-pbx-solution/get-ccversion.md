---
title: Get-CcVersion
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Devuelve la versión del dispositivo conector de nube. Get CCVersion sólo puede utilizarse en el equipo host del conector de la nube.
ms.openlocfilehash: 8391264603a73e3f594122dcdd2eb62b9ba19978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Devuelve la versión del dispositivo conector de nube. Get CCVersion sólo puede utilizarse en el equipo host del conector de la nube.
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Descripción detallada

Devuelve la versión del dispositivo conector de nube basado en secuencias de comandos de PowerShell instalados, los archivos en el directorio del dispositivo y las máquinas virtuales implementadas en el servidor host.
  
## <a name="parameters"></a>Parámetros

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Opcional   <br/> |System.String  <br/> |Tipo de versión. Valor del parámetro puede ser RunningScripts, RunningBits, BackupBits o todos. Valor predeterminado es RunningScripts.  <br/> |
   
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se muestra la versión de conector de nube de script se ejecuta actualmente en la consola de PowerShell abierta:
  
```
Get-CcVersion
```

### <a name="example-2"></a>Ejemplo 2

En el ejemplo siguiente se muestra la versión del conector de nube de los binarios de ejecución implementadas en las máquinas virtuales. Puede ver la versión en los nombres de máquina virtual de ejecución en el Administrador de Hyper-v:
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Ninguno. El cmdlet Get-CcVersion no acepta entrada canalizada.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="Examples"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="Examples"> </a>

Ninguno.
  

