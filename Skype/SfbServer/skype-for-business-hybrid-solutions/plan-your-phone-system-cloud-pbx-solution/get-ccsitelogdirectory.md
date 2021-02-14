---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: El cmdlet Get-CcSiteLogDirectory muestra el directorio actual donde se almacenan los registros de nivel de sitio para Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: cace3ce3757294adbb3c55db24c619925f55ce5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799890"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
El cmdlet Get-CcSiteLogDirectory muestra el directorio actual donde se almacenan los registros de nivel de sitio para Skype Empresarial Cloud Connector Edition. 
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se muestra la carpeta actual donde se almacenan los archivos de registro del sitio de Cloud Connector:
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La carpeta predeterminada es C:\Users \% userprofile%\CloudConnector\SiteRoot\Logs. Puede cambiar la carpeta ejecutando el cmdlet Set-CcSiteDirectory. No hay ningún cmdlet independiente que cambie solo la ubicación de la carpeta de registro sin cambiar el directorio del sitio.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Get-CcSiteLogDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

El comando devuelve una ruta de acceso de archivo.
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

