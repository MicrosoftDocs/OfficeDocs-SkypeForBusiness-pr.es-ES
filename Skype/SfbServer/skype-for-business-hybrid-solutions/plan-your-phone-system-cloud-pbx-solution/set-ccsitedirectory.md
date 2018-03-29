---
title: Conjunto de CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: El cmdlet Set-CcSiteDirectory establece el directorio en el que se almacenarán los archivos de configuración del nivel de sitio para Skype Empresarial Cloud Connector Edition. La carpeta contendrá el VHD base y los archivos de configuración de Cloud Connector.
ms.openlocfilehash: d34945a17f32c275240e2cef0435f6e0ca3e63a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccsitedirectory"></a>Conjunto de CcSiteDirectory
 
El cmdlet Set-CcSiteDirectory establece el directorio en el que se almacenarán los archivos de configuración del nivel de sitio para Skype Empresarial Cloud Connector Edition. La carpeta contendrá el VHD base y los archivos de configuración de Cloud Connector.
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se establece el directorio raíz del sitio en \\SiteShare\CloudConnector:
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Para proporcionar alta disponibilidad y afinidad de puerta de enlace, dispositivos de conector de nube pueden combinarse en sitios. Los usuarios se asignan a sitios en lugar de dispositivos de conector de nube. Cada sitio tiene una carpeta compartida donde se almacenan los archivos de instalación de VHD y nube de conector de base. Dispositivos utilizan esta carpeta durante la implementación. Esta carpeta debe compartirse con todos los otros equipos en un sitio de conector de nube.
  
La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\SiteRoot. La ruta se puede ver mediante el cmdlet Get-CcSiteDirectory.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|  Ruta de acceso <br/> |  Obligatorio <br/> | System.String <br/> |Proporciona la ruta a la carpeta donde se almacenarán los archivos de sitio de conector de nube.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Set-CcSiteDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

