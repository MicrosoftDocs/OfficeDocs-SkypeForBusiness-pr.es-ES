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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Devuelve la versión del dispositivo de Cloud Connector. Get-CCVersion solo se puede usar en el equipo host de Cloud Connector.
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799850"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Devuelve la versión del dispositivo de Cloud Connector. Get-CCVersion solo se puede usar en el equipo host de Cloud Connector.
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Descripción detallada

Devuelve la versión del dispositivo de Cloud Connector basada en scripts de PowerShell instalados, archivos en el directorio de dispositivos y las máquinas virtuales implementadas en el servidor host.
  
## <a name="parameters"></a>Parámetros

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Opcional  <br/> |System.String  <br/> |Tipo de versión. El valor del parámetro puede ser RunningScripts, RunningBits, BackupBits o All. El valor predeterminado es RunningScripts.  <br/> |
   
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se muestra la versión de Cloud Connector del script que se está ejecutando actualmente en la consola de PowerShell abierta:
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se muestra la versión de Cloud Connector de los archivos binarios actualmente en ejecución implementados en las máquinas virtuales. Puede ver la versión en los nombres de máquina virtual en ejecución en el Administrador de Hyper-v:
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Ninguno. El Get-CcVersion no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="Examples"> </a>

Ninguno.
  
## <a name="see-also"></a>Vea también
<a name="Examples"> </a>

Ninguno.
  

