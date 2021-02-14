---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporta la configuración de Skype Empresarial Cloud Connector Edition a un archivo local en el servidor host de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: cd0745081e3f069aaf58c9ffdbf24494bfb3ece1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801470"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Exporta la configuración de Skype Empresarial Cloud Connector Edition a un archivo local en el servidor host de Skype Empresarial Cloud Connector Edition.
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se establece el parámetro Path como una ruta de acceso de archivo completa y se exportan las configuraciones a ese archivo.
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="Examples"> </a>

El cmdlet Export-CcConfiguration permite guardar la configuración de Cloud Connector en un archivo en una ruta de acceso seleccionada. Este comando se introdujo en la versión 2.0 de Cloud Connector Edition.
  
## <a name="parameters"></a>Parámetros
<a name="Examples"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Path  <br/> |Obligatorio  <br/> |System.String  <br/> |Ruta de acceso completa al archivo donde se almacenarán las configuraciones de Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Ninguno. El Export-CcConfiguration no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="Examples"> </a>

Ninguno.
  
## <a name="see-also"></a>Vea también
<a name="Examples"> </a>

Import-CcConfiguration
  

