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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: El cmdlet Start-CcDownload descarga los bits Skype for Business Edición de conector de nube y el archivo msi sincrónicamente.
ms.openlocfilehash: 0d5974bb4d4fb5bc16f467410865fb571073246e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631574"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
El cmdlet Start-CcDownload descarga los bits Skype for Business Edición de conector de nube y el archivo msi sincrónicamente.
  
Con Cloud Connector versión 2.0 y versiones posteriores, también puede especificar el parámetro DownloadBitsOnly.
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se descargan sincrónicamente los bits de Cloud Connector y el archivo msi desde el sitio de descarga pública de Cloud Connector:
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se descargan los bits de Cloud Connector y el archivo msi de forma sincrónica desde un sitio de descarga privado:
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Ejemplo 3

El tercer ejemplo descarga los bits de Cloud Connector y el archivo msi de forma sincrónica desde un sitio de descarga privado.
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Si hay una nueva versión disponible en el sitio de descarga, Start-CcDownload descargará e instalará el archivo msi desde el sitio de descarga y, a continuación, descargará los bits de Cloud Connector sincrónicamente. Si no hay ninguna nueva versión del archivo msi, Start-CcDownload descargará solo los bits de Cloud Connector. Si los bits de Cloud Connector ya están descargados, Start-CcDownload no se ejecuta.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Opcional <br/> |System.String  <br/> | La dirección URL completa de una versión específica de Cloud Connector en el sitio de descarga privado. Use este parámetro con precaución: asegúrese de saber qué versión de Cloud Connector está descargando. <br/> |
|DownloadBitsOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Omita el paso para descargar e instalar MSI desde el sitio de descarga, descargue solo los bits de Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Start-CcDownload no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

Ninguno
  

