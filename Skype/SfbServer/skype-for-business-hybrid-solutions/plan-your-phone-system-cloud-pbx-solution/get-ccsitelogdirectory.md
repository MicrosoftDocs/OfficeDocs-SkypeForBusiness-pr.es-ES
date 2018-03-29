---
title: Get-CcSiteLogDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: 'El cmdlet Get-CcSiteLogDirectory muestra el directorio actual en el que se almacenan los registros a nivel de sitio de Skype Empresarial Cloud Connector Edition. '
ms.openlocfilehash: 68d89200ac8bf2aec32db45752d62d7ae205b830
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
El cmdlet Get-CcSiteLogDirectory muestra el directorio actual en el que se almacenan los registros a nivel de sitio de Skype Empresarial Cloud Connector Edition.  
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se muestra la carpeta actual donde se almacenan los archivos de registro para el sitio de conector de nube:
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs. Para cambiar la carpeta, ejecute el cmdlet Set-CcSiteDirectory. No hay un cmdlet aparte que cambie solo la ubicación de la carpeta de registros sin cambiar el directorio de sitios.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Get-CcSiteLogDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

El comando devuelve una ruta de archivo.
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Conjunto de CcSiteDirectory](set-ccsitedirectory.md)
  

