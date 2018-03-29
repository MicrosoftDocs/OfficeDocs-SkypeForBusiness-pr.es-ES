---
title: CcConfiguration de exportación
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporta el Skype para la configuración del conector de nube Business Edition a un archivo local en el Skype para servidor de conector de nube Business Edition.
ms.openlocfilehash: dfabf5f486190b13acd18f0ffcf67f9b7e37052c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfiguration"></a>CcConfiguration de exportación
 
Exporta el Skype para la configuración del conector de nube Business Edition a un archivo local en el Skype para servidor de conector de nube Business Edition.
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se establece el parámetro de ruta de acceso como una ruta de acceso completa al archivo y exporta configuraciones a ese archivo.
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="Examples"> </a>

El cmdlet Export-CcConfiguration le permite guardar la configuración del conector de la nube en un archivo en una ruta seleccionada. Este comando se introdujo en la nube conector Edition versión 2.0.
  
## <a name="parameters"></a>Parámetros
<a name="Examples"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Ruta de acceso  <br/> | Obligatorio  <br/> |System.String  <br/> |Ruta de acceso completa al archivo donde se almacenará la configuración de conector de nube.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Ninguno. El cmdlet Export-CcConfiguration no acepta entrada canalizada.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="Examples"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="Examples"> </a>

CcConfiguration de importación
  

