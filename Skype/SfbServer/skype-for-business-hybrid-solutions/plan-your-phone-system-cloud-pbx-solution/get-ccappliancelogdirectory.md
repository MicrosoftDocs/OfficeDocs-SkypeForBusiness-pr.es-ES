---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual donde se almacenan los registros de un dispositivo de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800830"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual donde se almacenan los registros de un dispositivo de Skype Empresarial Cloud Connector Edition.
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se muestra la carpeta actual donde se almacenan los registros del dispositivo actual de Cloud Connector:
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual donde se almacenan los registros de un dispositivo de Cloud Connector. La carpeta predeterminada es C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs. 
  
Puede cambiar el directorio con el cmdlet Set-CcApplianceDirectory datos. 
  
Nota: No hay ningún cmdlet que cambie solo la ubicación de la carpeta de registro sin cambiar el directorio del dispositivo.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Get-CcApplianceLogDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Este comando devuelve una ruta de acceso de archivo.
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

