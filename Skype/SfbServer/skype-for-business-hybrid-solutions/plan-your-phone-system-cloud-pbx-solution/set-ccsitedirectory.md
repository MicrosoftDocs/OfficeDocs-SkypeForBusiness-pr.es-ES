---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: El cmdlet Set-CcSiteDirectory establece el directorio donde se almacenarán los archivos de configuración de nivel Skype for Business Edición de conector de nube sitio. La carpeta contendrá los archivos de configuración de VHD base y Cloud Connector.
ms.openlocfilehash: e5685ac8c203338365141a4a7ba59daa82a06ef0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610537"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
El cmdlet Set-CcSiteDirectory establece el directorio donde se almacenarán los archivos de configuración de nivel Skype for Business Edición de conector de nube sitio. La carpeta contendrá los archivos de configuración de VHD base y Cloud Connector.
  
Este cmdlet se aplica a Skype for Business Edición de conector de nube 1.4.1, 1.4.2.
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se establece el directorio raíz del sitio \\ en SiteShare\CloudConnector:
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Para proporcionar afinidad de puerta de enlace y alta disponibilidad, los dispositivos de Cloud Connector se pueden combinar en sitios. Los usuarios se asignan a sitios en lugar de dispositivos de Cloud Connector. Cada sitio tiene una carpeta compartida donde se almacenan los archivos de instalación de VHD base y Cloud Connector. Los dispositivos usan esta carpeta durante la implementación. Esta carpeta debe compartirse con el resto de dispositivos de un sitio de Cloud Connector.
  
La carpeta predeterminada es C:\Users \% userprofile%\CloudConnector\SiteRoot. La ruta de acceso se puede ver mediante el cmdlet Get-CcSiteDirectory.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Ruta de acceso <br/> | Obligatorio <br/> | System.String <br/> |Proporciona la ruta de acceso a la carpeta donde se almacenarán los archivos de sitio de Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Set-CcSiteDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

