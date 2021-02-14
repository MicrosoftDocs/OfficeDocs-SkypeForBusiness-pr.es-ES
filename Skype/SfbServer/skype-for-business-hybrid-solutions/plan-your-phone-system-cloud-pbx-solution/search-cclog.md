---
title: Search-CcLog
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: El cmdlet Search-CcLog busca los registros de llamadas entrantes y salientes en el directorio de registro del dispositivo de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: a512d715f1640184217ce07e0b666954a6541fd2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824236"
---
# <a name="search-cclog"></a>Search-CcLog
 
El cmdlet Search-CcLog busca los registros de llamadas entrantes y salientes en el directorio de registro del dispositivo de Skype Empresarial Cloud Connector Edition.
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se buscan los registros de llamadas entrantes y salientes en el directorio de registro del dispositivo con el nombre de archivo predeterminado:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se buscan los registros de llamadas entrantes y salientes con la ruta de acceso y el nombre de archivo especificados:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Search-CsClsLogging proporciona una opción de línea de comandos para buscar los archivos de registro generados por el servicio de registro centralizado.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | Obligatorio <br/> |System.Datetime  <br/> | Fecha y hora de inicio de las entradas de registro que se buscarán. Se especifica en la zona horaria local. <br/> |
|EndTime  <br/> |Obligatorio  <br/> |System.Datetime  <br/> |Fecha y hora de finalización de las entradas de registro que se buscarán. Se especifica en la zona horaria local.  <br/> |
|FileName  <br/> |Necesario  <br/> |System.String  <br/> |Especifica la ruta de acceso completa del archivo de texto que contiene los resultados de la búsqueda.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Search-CcLog no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

