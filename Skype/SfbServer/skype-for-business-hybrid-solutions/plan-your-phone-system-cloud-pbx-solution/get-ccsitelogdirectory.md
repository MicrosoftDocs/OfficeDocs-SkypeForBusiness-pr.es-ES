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
ms.localizationpriority: medium
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: El cmdlet Get-CcSiteLogDirectory muestra el directorio actual donde se almacenan los registros de nivel Skype for Business Edición de conector de nube sitio.
ms.openlocfilehash: 65d99093f6390eade15e9783bd286bc438ede23d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616366"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
El cmdlet Get-CcSiteLogDirectory muestra el directorio actual donde se almacenan los registros de nivel Skype for Business Edición de conector de nube sitio. 
  
Este cmdlet se aplica a Skype for Business Edición de conector de nube 1.4.1, 1.4.2.
  
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

Ninguno. El cmdlet Get-CcSiteLogDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

El comando devuelve una ruta de acceso de archivo.
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

