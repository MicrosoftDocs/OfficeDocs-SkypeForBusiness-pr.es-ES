---
title: CcConfigurationSampleFile de exportación
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: El cmdlet Export-CcConfigurationSampleFile exporta un archivo de configuración (.ini) de muestra de Skype Empresarial Cloud Connector Edition al directorio de dispositivo de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo que se usará en la implementación.
ms.openlocfilehash: f91b9c7eb8ade4e5edcf1c83c5ddef205e0f3721
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfigurationsamplefile"></a>CcConfigurationSampleFile de exportación
 
El cmdlet Export-CcConfigurationSampleFile exporta un archivo de configuración (.ini) de muestra de Skype Empresarial Cloud Connector Edition al directorio de dispositivo de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo que se usará en la implementación.
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se descarga un archivo de configuración de ejemplo desde el sitio de Microsoft y lo escribe en el directorio de dispositivo del dispositivo conector de nube:
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La versión actual de nube conector requiere que se especifique varios parámetros en el archivo. ini. Por ejemplo, parámetros tales como las direcciones IP de máquinas virtuales para los componentes del conector de la nube, nombres de componentes, parámetros de puerta de enlace y así sucesivamente.
  
Este cmdlet, cuando se ejecuta en el equipo host del conector de la nube, descarga un archivo .ini de ejemplo con ejemplos de configuración desde el sitio de Microsoft. El cmdlet escribe el archivo en el directorio de dispositivo del dispositivo conector de nube. El directorio de dispositivos se especifica con el cmdlet Set-CcApplianceDirectory.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Export-CcConfigurationSampleFile no acepta entradas canalizadas. 
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Conjunto de CcApplianceDirectory](set-ccappliancedirectory.md)
  

