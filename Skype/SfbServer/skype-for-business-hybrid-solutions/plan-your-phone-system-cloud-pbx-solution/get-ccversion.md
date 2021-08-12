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
ms.openlocfilehash: d3da9813fd67228f8e198cd21edce3cc187ac9359617eb660a352b38c51a95ba
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349512"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Devuelve la versión del dispositivo de Cloud Connector. Get-CCVersion solo se puede usar en el equipo host de Cloud Connector.
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Descripción detallada

Devuelve la versión del dispositivo de Cloud Connector basada en scripts de PowerShell instalados, archivos en el directorio del dispositivo y las máquinas virtuales implementadas en el servidor host.
  
## <a name="parameters"></a>Parámetros

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Opcional  <br/> |System.String  <br/> |Tipo de versión. El valor del parámetro puede ser RunningScripts, RunningBits, BackupBits o All. El valor predeterminado es RunningScripts.  <br/> |
   
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se muestra la versión de Cloud Connector del script que se está ejecutando actualmente en la consola abierta de PowerShell:
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>Ejemplo 2

En el ejemplo siguiente se muestra la versión de Cloud Connector de los archivos binarios que se están ejecutando actualmente implementados en las máquinas virtuales. Puede ver la versión en los nombres de máquina virtual en ejecución en el Administrador de Hyper-v:
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Ninguno. El cmdlet Get-CcVersion no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="Examples"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="Examples"> </a>

Ninguno.
  

