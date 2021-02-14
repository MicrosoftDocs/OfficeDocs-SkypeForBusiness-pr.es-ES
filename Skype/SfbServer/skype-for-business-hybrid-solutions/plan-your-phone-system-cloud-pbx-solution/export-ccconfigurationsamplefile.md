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
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: El cmdlet Export-CcConfigurationSampleFile exporta un archivo de configuración de ejemplo (.ini) de Skype Empresarial Cloud Connector Edition al directorio de dispositivos de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo que se usará para la implementación.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801010"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
El cmdlet Export-CcConfigurationSampleFile exporta un archivo de configuración de ejemplo (.ini) de Skype Empresarial Cloud Connector Edition al directorio de dispositivos de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo que se usará para la implementación.
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se descarga un archivo de configuración de ejemplo del sitio de Microsoft y se escribe en el directorio de dispositivos del dispositivo de Cloud Connector:
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La versión actual de Cloud Connector requiere que proporcione varios parámetros en el archivo .ini; por ejemplo, parámetros como las direcciones IP de las máquinas virtuales para los componentes de Cloud Connector, los nombres de componentes, los parámetros de puerta de enlace, entre otros.
  
Este cmdlet, cuando se ejecuta en el equipo host de Cloud Connector, descarga un archivo .ini de ejemplo con ejemplos de configuración del sitio de Microsoft. El cmdlet escribe el archivo en el directorio de dispositivos del dispositivo de Cloud Connector. El directorio de dispositivos se especifica mediante el cmdlet Set-CcApplianceDirectory aplicación.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Export-CcConfigurationSampleFile no acepta entradas canalizadas. 
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

