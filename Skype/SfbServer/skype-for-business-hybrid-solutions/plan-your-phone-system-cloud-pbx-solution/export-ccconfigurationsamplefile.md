---
title: Export-CcConfigurationSampleFile
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
ms.localizationpriority: medium
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: El cmdlet Export-CcConfigurationSampleFile exporta un Skype for Business Edición de conector de nube de configuración de ejemplo (.ini) al directorio del dispositivo de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo que se usará para la implementación.
ms.openlocfilehash: 409514761c3bfeccebb671d289201fc67f58d220
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603669"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
El cmdlet Export-CcConfigurationSampleFile exporta un Skype for Business Edición de conector de nube de configuración de ejemplo (.ini) al directorio del dispositivo de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo que se usará para la implementación.
  
Este cmdlet se aplica a Skype for Business Edición de conector de nube 1.4.1, 1.4.2.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se descarga un archivo de configuración de ejemplo desde el sitio de Microsoft y se escribe en el directorio del dispositivo de Cloud Connector:
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La versión actual de Cloud Connector requiere que proporcione varios parámetros en el .ini archivo; por ejemplo, parámetros como las direcciones IP de las máquinas virtuales para los componentes de Cloud Connector, los nombres de componentes, los parámetros de puerta de enlace, entre otros.
  
Este cmdlet, cuando se ejecuta en el equipo host de Cloud Connector, descarga un archivo de .ini de ejemplo con ejemplos de configuración del sitio de Microsoft. El cmdlet escribe el archivo en el directorio del dispositivo del dispositivo de Cloud Connector. El directorio del dispositivo se especifica mediante el cmdlet Set-CcApplianceDirectory aplicación.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Export-CcConfigurationSampleFile no acepta entradas canalizadas. 
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

