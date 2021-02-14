---
title: Get-CcSiteDirectory
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
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: El cmdlet Get-CcSiteDirectory muestra el directorio actual donde se almacenan los archivos de configuración de nivel de sitio. La carpeta contiene el VHD base y los archivos de instalación de Skype Empresarial Cloud Connector Edition. Esta carpeta debe compartirse con todos los demás dispositivos de un sitio de Cloud Connector.
ms.openlocfilehash: 6722b66f6c71feec158adaf442f9e57ef9943c84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799870"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
El cmdlet Get-CcSiteDirectory muestra el directorio actual donde se almacenan los archivos de configuración de nivel de sitio. La carpeta contiene el VHD base y los archivos de instalación de Skype Empresarial Cloud Connector Edition. Esta carpeta debe compartirse con todos los demás dispositivos de un sitio de Cloud Connector.
  
Este cmdlet se aplica a Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se muestra la carpeta actual donde se almacenan los archivos de configuración y de máquinas virtuales de los componentes de Cloud Connector:
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Para proporcionar afinidad de puerta de enlace y alta disponibilidad, los dispositivos de Cloud Connector se pueden combinar en sitios. Los usuarios se asignan a sitios en lugar de dispositivos de Cloud Connector. Cada sitio tiene una carpeta compartida donde se almacenan los archivos base de instalación de VHD y Cloud Connector. Los dispositivos usan esta carpeta durante la implementación. La carpeta predeterminada es C:\Users \% userprofile%\CloudConnector\SiteRoot. Puede cambiar la ruta de acceso mediante el cmdlet Set-CcSiteDirectory.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Get-CcSiteDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Este comando devuelve una ruta de acceso de archivo.
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

