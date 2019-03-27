---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: El cmdlet Start-CcDownload descarga el Skype para bits Business Edition de conector en la nube y el archivo msi de forma sincrónica.
ms.openlocfilehash: cc157825df75a4534422cb0a2fd07abb0ae0daea
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893841"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
El cmdlet Start-CcDownload descarga el Skype para bits Business Edition de conector en la nube y el archivo msi de forma sincrónica.
  
Con la nube conector versión 2.0 y versiones posterior, también puede especificar el parámetro DownloadBitsOnly.
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se descarga los bits de conector en la nube y el archivo msi de forma sincrónica desde el sitio de descarga pública de conector en la nube:
  
```
Start-CcDownload
```

### <a name="example-2"></a>Ejemplo 2

En el ejemplo siguiente se descarga los bits de conector en la nube y el archivo msi de forma sincrónica desde un sitio de descarga privada:
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Ejemplo 3

El tercer ejemplo descarga los bits de conector en la nube y el archivo msi de forma sincrónica desde un sitio de descarga privada.
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Si hay una nueva versión en el sitio de descarga, inicio CcDownload descargar e instalar el archivo msi desde el sitio de descarga y, a continuación, descargue los bits de conector en la nube de forma sincrónica. Si no hay ninguna versión nueva del archivo msi, inicio CcDownload descargará sólo los bits de conector en la nube. Si ya se descargan los bits de conector en la nube, CcDownload de inicio no se ejecuta.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Opcional  <br/> |System.String  <br/> | Sitio de descarga de la dirección URL completa de una versión específica de conector en la nube en privado. Utilice este parámetro con precaución: asegúrese de tener en cuenta qué versión del conector de la nube de descarga. <br/> |
|DownloadBitsOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Omitir el paso para descargar e instalar MSI desde el sitio de descarga, descargue sólo los bits de conector en la nube.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Start-CcDownload no acepta entradas transferidas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno 
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

Ninguno
  

