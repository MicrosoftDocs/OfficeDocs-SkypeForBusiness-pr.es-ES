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
ms.localizationpriority: medium
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: El cmdlet Get-CcSiteDirectory muestra el directorio actual donde se almacenan los archivos de configuración de nivel de sitio. La carpeta contiene el VHD base y los Skype for Business Edición de conector de nube de instalación. Esta carpeta debe compartirse con todos los demás dispositivos de un sitio de Cloud Connector.
ms.openlocfilehash: 04b1460b9743c3d19ca4db77f67d057d400f400b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616376"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
El cmdlet Get-CcSiteDirectory muestra el directorio actual donde se almacenan los archivos de configuración de nivel de sitio. La carpeta contiene el VHD base y los Skype for Business Edición de conector de nube de instalación. Esta carpeta debe compartirse con todos los demás dispositivos de un sitio de Cloud Connector.
  
Este cmdlet se aplica a Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se muestra la carpeta actual donde se almacenan los archivos de configuración y máquinas virtuales de los componentes de Cloud Connector:
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Para proporcionar afinidad de puerta de enlace y alta disponibilidad, los dispositivos de Cloud Connector se pueden combinar en sitios. Los usuarios se asignan a sitios en lugar de dispositivos de Cloud Connector. Cada sitio tiene una carpeta compartida donde se almacenan los archivos de instalación de VHD base y Cloud Connector. Los dispositivos usan esta carpeta durante la implementación. La carpeta predeterminada es C:\Users \% userprofile%\CloudConnector\SiteRoot. Puede cambiar la ruta de acceso mediante el cmdlet Set-CcSiteDirectory.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Get-CcSiteDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Este comando devuelve una ruta de acceso de archivo.
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

