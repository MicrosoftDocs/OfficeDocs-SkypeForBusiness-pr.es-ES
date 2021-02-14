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
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: El cmdlet Set-CcSiteDirectory establece el directorio donde se almacenarán los archivos de configuración de nivel de sitio para Skype Empresarial Cloud Connector Edition. La carpeta contendrá el VHD base y los archivos de configuración de Cloud Connector.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824194"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
El cmdlet Set-CcSiteDirectory establece el directorio donde se almacenarán los archivos de configuración de nivel de sitio para Skype Empresarial Cloud Connector Edition. La carpeta contendrá el VHD base y los archivos de configuración de Cloud Connector.
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.
  
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

Para proporcionar afinidad de puerta de enlace y alta disponibilidad, los dispositivos de Cloud Connector se pueden combinar en sitios. Los usuarios se asignan a sitios en lugar de dispositivos de Cloud Connector. Cada sitio tiene una carpeta compartida donde se almacenan los archivos base de instalación de VHD y Cloud Connector. Los dispositivos usan esta carpeta durante la implementación. Esta carpeta debe compartirse con todos los demás dispositivos de un sitio de Cloud Connector.
  
La carpeta predeterminada es C:\Users \% userprofile%\CloudConnector\SiteRoot. La ruta de acceso se puede ver con el cmdlet Get-CcSiteDirectory búsqueda.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Path <br/> | Obligatorio <br/> | System.String <br/> |Proporciona la ruta de acceso a la carpeta donde se almacenarán los archivos del sitio de Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Set-CcSiteDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

