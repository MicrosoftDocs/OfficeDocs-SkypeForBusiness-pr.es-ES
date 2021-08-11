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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporta la Skype for Business Edición de conector de nube a un archivo local en el Skype for Business Edición de conector de nube host.
ms.openlocfilehash: f34f8454dfc3129be50b26114f71fdeee4a4b633f66ca9f80dc621c51c5af6ad
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288848"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Exporta la Skype for Business Edición de conector de nube a un archivo local en el Skype for Business Edición de conector de nube host.
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se establece el parámetro Path como una ruta de acceso de archivo completa y se exportan configuraciones a ese archivo.
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="Examples"> </a>

El cmdlet Export-CcConfiguration permite guardar la configuración de Cloud Connector en un archivo en una ruta de acceso seleccionada. Este comando se introdujo en Cloud Connector Edition versión 2.0.
  
## <a name="parameters"></a>Parámetros
<a name="Examples"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Path  <br/> |Obligatorio  <br/> |System.String  <br/> |Ruta de acceso de archivo completa en la que se almacenarán las configuraciones de Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Ninguno. El cmdlet Export-CcConfiguration no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="Examples"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="Examples"> </a>

Import-CcConfiguration
  

