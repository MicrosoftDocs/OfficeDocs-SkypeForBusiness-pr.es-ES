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
description: Importa la Skype for Business Edición de conector de nube de un archivo local al servidor host de Cloud Connector.
ms.openlocfilehash: 4ac32f460c2c493f5d78f1a38adcdd0728763bbbcf57a67470823fb88d407d09
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349502"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importa la Skype for Business Edición de conector de nube de un archivo local al servidor host de Cloud Connector.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se copia CloudConnector.ini del directorio del dispositivo de la instancia de Cloud Connector en el directorio %SystemDrive%\ProgramData\CloudConnector:
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>Descripción detallada
<a name="Examples"> </a>

Este cmdlet copia el CloudConnector.ini del directorio del dispositivo de Cloud Connector en el directorio %SystemDrive%\ProgramData\CloudConnector. El directorio del dispositivo se especifica mediante el cmdlet Set-CcApplianceDirectory aplicación. El cmdlet sobrescribirá cualquier archivo existente en %SystemDrive%\ProgramData\CloudConnector. Este comando se aplica a Cloud Connector Edition versión 2.0.1 y versiones posteriores.
  
## <a name="parameters"></a>Parámetros
<a name="Examples"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Sobrescribir el archivo existente en %SystemDrive%\ProgramData\CloudConnector sin notificación.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Ninguno. El cmdlet Import-CcConfiguration no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="Examples"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="Examples"> </a>

Export-CcConfiguration
  

