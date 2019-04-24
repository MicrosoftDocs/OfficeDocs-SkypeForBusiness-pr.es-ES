---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Devuelve la versión del dispositivo de conector en la nube. Get-CCVersion sólo puede utilizarse en el equipo host del conector en la nube.
ms.openlocfilehash: 5e5428e53d53eec66bafa9eb566059ef1b5a5833
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233760"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Devuelve la versión del dispositivo de conector en la nube. Get-CCVersion sólo puede utilizarse en el equipo host del conector en la nube.
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Descripción detallada

Devuelve la versión del dispositivo de conector en la nube basado en los scripts de PowerShell instalados, los archivos en el directorio del dispositivo y las máquinas virtuales que se implementan en el servidor host.
  
## <a name="parameters"></a>Parámetros

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Opcional  <br/> |System.String  <br/> |Tipo de versión. Valor del parámetro puede ser RunningScripts, RunningBits, BackupBits o todos. Valor predeterminado es RunningScripts.  <br/> |
   
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se muestra la versión de conector en la nube de la secuencia de comandos que se está ejecutando en la consola de PowerShell abierta:
  
```
Get-CcVersion
```

### <a name="example-2"></a>Ejemplo 2

En el ejemplo siguiente se muestra la versión de conector en la nube de los archivos binarios que se está ejecutando de implementada en las máquinas virtuales. Puede ver la versión en los nombres de máquina virtual que se está ejecutando en el Administrador de Hyper-v:
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Ninguno. El cmdlet Get-CcVersion no acepta entradas transferidas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="Examples"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="Examples"> </a>

Ninguno.
  

