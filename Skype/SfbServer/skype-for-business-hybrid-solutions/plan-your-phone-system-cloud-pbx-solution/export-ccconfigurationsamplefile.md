---
title: Export-CcConfigurationSampleFile
ms.reviewer: ''
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
ms.openlocfilehash: 3154ff3492899de244c3033e4e35345132d04f20
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233991"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
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

En el ejemplo siguiente se descarga un archivo de configuración de ejemplo desde el sitio de Microsoft y los escribe en el directorio de dispositivo del dispositivo conector en la nube:
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La versión actual del conector en la nube, es necesario proporcionar varios parámetros en el archivo .ini; Por ejemplo, parámetros, como las direcciones IP de máquinas virtuales para los componentes de los conectores de la nube, nombres de componente, parámetros de puerta de enlace y así sucesivamente.
  
Este cmdlet, cuando se ejecuta en el equipo host del conector en la nube, descarga un archivo .ini de ejemplo con ejemplos de la configuración del sitio de Microsoft. El cmdlet escribe el archivo en el directorio de dispositivo del dispositivo conector en la nube. El directorio de dispositivos se especifica con el cmdlet Set-CcApplianceDirectory.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Export-CcConfigurationSampleFile no acepta entradas canalizadas. 
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

