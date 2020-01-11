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
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: El cmdlet Export-CcConfigurationSampleFile exporta un archivo de configuración (.ini) de muestra de Skype Empresarial Cloud Connector Edition al directorio de dispositivo de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo que se usará en la implementación.
ms.openlocfilehash: b62d5d7ffa9e8f10aeae509201c5aa0a1e7fa0a4
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003430"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
El cmdlet Export-CcConfigurationSampleFile exporta un archivo de configuración (.ini) de muestra de Skype Empresarial Cloud Connector Edition al directorio de dispositivo de un dispositivo de Cloud Connector. Puede modificar y cambiar el nombre del archivo que se usará en la implementación.
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se descarga un archivo de configuración de ejemplo del sitio de Microsoft y se escribe en el directorio del equipo del dispositivo de conector de nube:
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La versión actual del conector de nube requiere que proporcione varios parámetros en el archivo. ini; por ejemplo, parámetros como las direcciones IP de las máquinas virtuales para los componentes del conector de nube, los nombres de componentes, los parámetros de puerta de enlace, etc.
  
Este cmdlet, cuando se ejecuta en la máquina host del conector de nube, descarga un archivo. ini de ejemplo con ejemplos de configuración del sitio de Microsoft. El cmdlet escribe el archivo en el directorio del equipo del dispositivo de conector de nube. El directorio de dispositivos se especifica con el cmdlet Set-CcApplianceDirectory.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Export-CcConfigurationSampleFile no acepta entradas canalizadas. 
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

