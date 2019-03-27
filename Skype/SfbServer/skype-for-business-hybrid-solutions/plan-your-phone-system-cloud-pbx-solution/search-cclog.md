---
title: Search-CcLog
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: El cmdlet Search-CcLog busca los registros de llamadas entrantes y salientes en el directorio de registros del dispositivo de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: e11e82ba105ed58efa6892165a19c6a4c4de0429
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892768"
---
# <a name="search-cclog"></a>Search-CcLog
 
El cmdlet Search-CcLog busca los registros de llamadas entrantes y salientes en el directorio de registros del dispositivo de Skype Empresarial Cloud Connector Edition.
  
```
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se buscan los registros de llamadas entrantes y salientes en el directorio de registros del dispositivo mediante el nombre de archivo predeterminado:
  
```
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se buscan los registros de llamadas entrantes y salientes mediante la ruta y el nombre de un archivo determinado:
  
```
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Search-CsClsLogging ofrece una opción de línea de comandos para buscar los archivos de registro del servicio de registro centralizado.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | Requerido <br/> |System.Datetime  <br/> | Fecha y hora inicial de las entradas del registro que se buscarán. Se especifica en la zona horaria local. <br/> |
|EndTime  <br/> |Requerido  <br/> |System.Datetime  <br/> |Fecha y hora final de las entradas del registro que se buscarán. Se especifica en la zona horaria local.  <br/> |
|FileName  <br/> |Obligatorio  <br/> |System.String  <br/> |Especifica la ruta completa del archivo de texto que contiene los resultados de la búsqueda.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Search-CcLog acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

