---
title: Get-CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: El cmdlet Get-CcSiteDirectory muestra el directorio actual en el que se almacenan los archivos de configuración del nivel de sitio. La carpeta contiene el VHD base y los archivos de instalación de Skype Empresarial Cloud Connector Edition. Esta carpeta debe compartirse con todos los otros equipos de un sitio de conector de nube.
ms.openlocfilehash: e75e20a18960510bf75a8ca4cfc97ffd9daa894f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
El cmdlet Get-CcSiteDirectory muestra el directorio actual en el que se almacenan los archivos de configuración del nivel de sitio. La carpeta contiene el VHD base y los archivos de instalación de Skype Empresarial Cloud Connector Edition. Esta carpeta debe compartirse con todos los otros equipos de un sitio de conector de nube.
  
Este cmdlet se aplica a Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se muestra la carpeta actual donde se almacenan los archivos de configuración de máquinas virtuales y componentes de los conectores de la nube:
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Para proporcionar alta disponibilidad y afinidad de puerta de enlace, dispositivos de conector de nube pueden combinarse en sitios. Los usuarios se asignan a sitios en lugar de dispositivos de conector de nube. Cada sitio tiene una carpeta compartida donde se almacenan los archivos de instalación de VHD y nube de conector de base. Dispositivos utilizan esta carpeta durante la implementación. La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\SiteRoot. Puede cambiar la ruta de acceso mediante el cmdlet Set-CcSiteDirectory.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Get-CcSiteDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Este comando devuelve una ruta de archivo.
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Conjunto de CcSiteDirectory](set-ccsitedirectory.md)
  

