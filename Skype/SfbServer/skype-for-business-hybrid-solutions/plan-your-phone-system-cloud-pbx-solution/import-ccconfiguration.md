---
title: CcConfiguration de importación
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importa el Skype para la configuración del conector de nube Business Edition desde un archivo local en el servidor de host de conector de nube.
ms.openlocfilehash: 46f4099258ce4090fa23ec980801e55f7300895f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="import-ccconfiguration"></a>CcConfiguration de importación
 
Importa el Skype para la configuración del conector de nube Business Edition desde un archivo local en el servidor de host de conector de nube.
  
```

Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

El ejemplo siguiente copia la CloudConnector.ini desde el directorio del dispositivo de la instancia del conector de nube al directorio %SystemDrive%\ProgramData\CloudConnector:
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a>Descripción detallada
<a name="Examples"> </a>

Este cmdlet copia el CloudConnector.ini desde el directorio de dispositivo del dispositivo conector de nube en el directorio %SystemDrive%\ProgramData\CloudConnector. El directorio de dispositivos se especifica con el cmdlet Set-CcApplianceDirectory. El cmdlet sobrescribirá cualquier archivo existente en % SystemDrive%\ProgramData\CloudConnector. Este comando se aplica a la nube conector Edition versión 2.0.1 y posteriores.
  
## <a name="parameters"></a>Parámetros
<a name="Examples"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Sobrescribir un archivo existente en %SystemDrive%\ProgramData\CloudConnector sin notificación.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Ninguno. El cmdlet Import-CcConfiguration no acepta entrada canalizada.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="Examples"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="Examples"> </a>

CcConfiguration de exportación
  

