---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importa la configuración de Skype empresarial Cloud Connector Edition de un archivo local al servidor host del conector de nube.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799860"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importa la configuración de Skype empresarial Cloud Connector Edition de un archivo local al servidor host del conector de nube.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se copia el CloudConnector. ini del directorio del dispositivo de la instancia de Cloud Connector en el directorio%SystemDrive%\ProgramData\CloudConnector:
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>Descripción detallada
<a name="Examples"> </a>

Este cmdlet copia el CloudConnector. ini desde el directorio del equipo del dispositivo del conector de nube en el directorio de%SystemDrive%\ProgramData\CloudConnector. El directorio de dispositivos se especifica con el cmdlet Set-CcApplianceDirectory. El cmdlet sobrescribirá cualquier archivo existente en%SystemDrive%\ProgramData\CloudConnector. Este comando se aplica a la versión 2.0.1 de Cloud Connector Edition y posteriores.
  
## <a name="parameters"></a>Parámetros
<a name="Examples"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Sobrescribir el archivo existente en%SystemDrive%\ProgramData\CloudConnector sin notificación.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Ninguno. El cmdlet Import-CcConfiguration no acepta la entrada canalizada.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="Examples"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="Examples"> </a>

Export-CcConfiguration
  

