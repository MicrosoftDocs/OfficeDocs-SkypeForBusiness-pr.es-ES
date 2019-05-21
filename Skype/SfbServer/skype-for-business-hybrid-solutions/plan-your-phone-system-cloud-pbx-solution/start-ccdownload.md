---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: El cmdlet Start-CcDownload descarga el archivo MSI y los bits de Skype empresarial Cloud Connector Edition de forma sincrónica.
ms.openlocfilehash: 184c15d1932a179bb9ae07da515eeacfc115dfae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286946"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
El cmdlet Start-CcDownload descarga el archivo MSI y los bits de Skype empresarial Cloud Connector Edition de forma sincrónica.
  
Con la versión 2,0 y posteriores del conector para la nube, también puede especificar el parámetro DownloadBitsOnly.
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se descarga el archivo MSI y los bits de conector de la nube de forma sincrónica desde el sitio de descarga pública de conector en la nube:
  
```
Start-CcDownload
```

### <a name="example-2"></a>Ejemplo 2

El siguiente ejemplo descarga los bits de conector de la nube y el archivo MSI de forma sincrónica desde un sitio de descarga privada:
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Ejemplo 3

El tercer ejemplo descarga los bits de conector de la nube y el archivo MSI de forma sincrónica desde un sitio de descarga privada.
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Si hay una nueva versión disponible en el sitio de descarga, Start-CcDownload se descargará e instalará el archivo MSI desde el sitio de descarga y, a continuación, descargará los bits de conector de nube de forma sincrónica. Si no hay ninguna versión nueva del archivo MSI, Start-CcDownload se descargará solo los bits de conector de la nube. Si los bits de conector de la nube ya se han descargado, Start-CcDownload no se ejecuta.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Opcional  <br/> |System.String  <br/> | La dirección URL completa de una versión específica del conector de nube en el sitio de descarga privada. Use este parámetro con precaución: Asegúrese de estar al tanto de qué versión del conector de nube está descargando. <br/> |
|DownloadBitsOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Omita el paso para descargar e instalar MSI desde el sitio de descarga, descargar solo los bits de conector de la nube.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Start-CcDownload no acepta la entrada canalizada.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno 
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

Ninguno
  

