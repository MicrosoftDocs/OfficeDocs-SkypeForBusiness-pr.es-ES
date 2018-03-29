---
title: Get-CcApplianceLogDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual en el que se almacenan los registros de un dispositivo de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 9b7d4853deb9ab16c7ae61279a20a30778774072
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual en el que se almacenan los registros de un dispositivo de Skype Empresarial Cloud Connector Edition.
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se muestra la carpeta actual donde se almacenan los registros para el dispositivo actual del conector de la nube:
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual donde se almacenan los registros para un dispositivo conector de nube. La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs. 
  
Puede cambiar el directorio con el cmdlet Set-CcApplianceDirectory.  
  
Nota: no hay ningún cmdlet que cambie solo la ubicación de la carpeta de registros sin cambiar el directorio de dispositivos.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Get-CcApplianceLogDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Este comando devuelve una ruta de archivo.
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Conjunto de CcApplianceDirectory](set-ccappliancedirectory.md)
  

