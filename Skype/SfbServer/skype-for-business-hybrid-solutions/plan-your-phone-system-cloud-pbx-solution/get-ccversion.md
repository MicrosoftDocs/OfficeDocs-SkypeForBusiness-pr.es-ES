---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Devuelve la versión del dispositivo de conector de nube. Get-CCVersion solo se puede usar en la máquina host del conector en la nube.
ms.openlocfilehash: b002b4a9f0cae34a2cdd7b8817e86a3e4ec2eb9a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287254"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Devuelve la versión del dispositivo de conector de nube. Get-CCVersion solo se puede usar en la máquina host del conector en la nube.
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Descripción detallada

Devuelve la versión del dispositivo de conector de nube en función de los scripts de PowerShell instalados, los archivos del directorio del equipo y las máquinas virtuales implementadas en el servidor host.
  
## <a name="parameters"></a>Parámetros

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Opcional  <br/> |System.String  <br/> |Tipo de versión. El valor del parámetro puede ser RunningScripts, RunningBits, BackupBits o ALL. El valor predeterminado es RunningScripts.  <br/> |
   
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se muestra la versión del conector de nube del script que se está ejecutando actualmente en la consola de PowerShell abierta:
  
```
Get-CcVersion
```

### <a name="example-2"></a>Ejemplo 2

En el ejemplo siguiente se muestra la versión de conector de nube de los binarios que se han implementado en las máquinas virtuales. Puede ver la versión en los nombres de la máquina virtual en ejecución en el administrador de Hyper-v:
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Ninguno. El cmdlet Get-CcVersion no acepta la entrada canalizada.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="Examples"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="Examples"> </a>

Ninguno.
  

