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
description: Importa el Skype para la configuración del conector de nube Business Edition desde un archivo local en el servidor de host de conector en la nube.
ms.openlocfilehash: c48ce321b4cf40626cc67de8ff32107bf08e5443
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569729"
---
# <a name="import-ccconfiguration"></a>CcConfiguration de importación
 
Importa el Skype para la configuración del conector de nube Business Edition desde un archivo local en el servidor de host de conector en la nube.
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

El siguiente ejemplo copia la CloudConnector.ini desde el directorio de dispositivo de la instancia del conector en la nube al directorio %SystemDrive%\ProgramData\CloudConnector:
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a>Descripción detallada
<a name="Examples"> </a>

Este cmdlet copia la CloudConnector.ini desde el directorio de dispositivo del dispositivo conector en la nube en el directorio %SystemDrive%\ProgramData\CloudConnector. El directorio de dispositivos se especifica con el cmdlet Set-CcApplianceDirectory. El cmdlet sobrescribirá los archivos existentes en % SystemDrive%\ProgramData\CloudConnector. Este comando se aplica a la nube conector Edition versión 2.0.1 y versiones posteriores.
  
## <a name="parameters"></a>Parámetros
<a name="Examples"> </a>

|**Parámetro**|**Requerida.**|**Tipo de**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Sobrescribir archivo existente en %SystemDrive%\ProgramData\CloudConnector sin notificación.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Ninguno. El cmdlet Import-CcConfiguration no acepta entradas transferidas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="Examples"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="Examples"> </a>

Export-CcConfiguration
  

