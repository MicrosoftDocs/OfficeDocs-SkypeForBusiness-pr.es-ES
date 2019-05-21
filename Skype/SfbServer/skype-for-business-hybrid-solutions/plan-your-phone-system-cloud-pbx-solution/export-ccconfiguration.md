---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporta la configuración de Skype empresarial Cloud Connector Edition a un archivo local en el servidor host de Skype Cloud Connector Edition.
ms.openlocfilehash: 7548b2fba602364d98c7540607660ccc57710654
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287422"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Exporta la configuración de Skype empresarial Cloud Connector Edition a un archivo local en el servidor host de Skype Cloud Connector Edition.
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se establece el parámetro Path como una ruta de acceso de archivo completa y se exportan las configuraciones a ese archivo.
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="Examples"> </a>

El cmdlet Export-CcConfiguration le permite guardar la configuración del conector de la nube en un archivo en una ruta de acceso seleccionada. Este comando se introdujo en la versión 2,0 de Cloud Connector Edition.
  
## <a name="parameters"></a>Parámetros
<a name="Examples"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Ruta de acceso  <br/> |Obligatorio  <br/> |System.String  <br/> |Ruta de acceso completa del archivo donde se almacenarán las configuraciones del conector de la nube.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Ninguno. El cmdlet Export-CcConfiguration no acepta la entrada canalizada.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="Examples"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="Examples"> </a>

Import-CcConfiguration
  

