---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporta el Skype para la configuración del conector de nube Business Edition a un archivo local en el Skype para servidor de host de Business Edition de conector en la nube.
ms.openlocfilehash: 8afca55e6727c84c579957de9e2010e84a72fb15
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894240"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Exporta el Skype para la configuración del conector de nube Business Edition a un archivo local en el Skype para servidor de host de Business Edition de conector en la nube.
  
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

El cmdlet Export-CcConfiguration permite guardar la configuración del conector de nube en un archivo en una ruta de acceso seleccionado. Este comando se introdujo en la nube conector Edition versión 2.0.
  
## <a name="parameters"></a>Parámetros
<a name="Examples"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Ruta de acceso  <br/> |Obligatorio  <br/> |System.String  <br/> |Ruta de acceso completa al archivo donde se almacenarán las configuraciones de conector en la nube.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Ninguno. El cmdlet Export-CcConfiguration no acepta entradas transferidas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="Examples"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="Examples"> </a>

Import-CcConfiguration
  

