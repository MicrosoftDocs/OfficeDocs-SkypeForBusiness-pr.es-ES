---
title: Inicio CcDownload
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: El cmdlet Start-CcDownload descarga el Skype para bits de conector de nube Business Edition y el archivo msi sincrónicamente.
ms.openlocfilehash: aec8d5c1848e7e55d6ed4b7e4d3633942f74ab55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="start-ccdownload"></a>Inicio CcDownload
 
El cmdlet Start-CcDownload descarga el Skype para bits de conector de nube Business Edition y el archivo msi sincrónicamente.
  
Con conector de nube 2.0 y versiones posteriores, también puede especificar el parámetro DownloadBitsOnly.
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

El ejemplo siguiente descarga los bits de la nube de conector y el archivo msi sincrónicamente desde el sitio de descarga pública de conector de nube:
  
```
Start-CcDownload
```

### <a name="example-2"></a>Ejemplo 2

En el ejemplo siguiente descarga los bits de la nube de conector y el archivo msi sincrónicamente desde un sitio de descarga privada:
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Ejemplo 3

El tercer ejemplo descarga los bits de la nube de conector y el archivo msi sincrónicamente desde un sitio de descarga privada.
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Si hay una nueva versión disponible en el sitio de descarga, inicio CcDownload descargar e instalar el archivo msi desde el sitio de descarga y, a continuación, descargar los bits de nube conector sincrónicamente. Si no hay ninguna versión nueva del archivo msi, inicio CcDownload descargará sólo los bits del conector de la nube. Si ya se descargan los bits del conector de la nube, CcDownload de inicio no se ejecuta.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Opcional  <br/> |System.String  <br/> | Sitio de descarga de la dirección URL completa de una versión específica de conector de nube en privado. Utilice este parámetro con precaución: asegúrese de que es consciente de qué versión de conector de nube está descargando. <br/> |
|DownloadBitsOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Omitir el paso para descargar e instalar el MSI desde el sitio de descarga, descargue sólo los bits del conector de la nube.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Start-CcDownload no acepta entrada canalizada.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

Ninguno
  

