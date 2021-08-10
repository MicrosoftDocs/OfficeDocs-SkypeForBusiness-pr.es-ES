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
description: El cmdlet Search-CcLog busca en los registros de llamadas entrantes y salientes en el Skype for Business Edición de conector de nube registro del dispositivo.
ms.openlocfilehash: 5fd062295ac9145660ca9a53f56973f77783cd9730993d958c7348b7761c4387
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306611"
---
# <a name="search-cclog"></a>Search-CcLog
 
El cmdlet Search-CcLog busca en los registros de llamadas entrantes y salientes en el Skype for Business Edición de conector de nube registro del dispositivo.
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se buscan los registros de llamadas entrantes y salientes en el directorio de registro del dispositivo con el nombre de archivo predeterminado:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>Ejemplo 2

El siguiente ejemplo busca en los registros de llamadas entrantes y salientes con la ruta de acceso y el nombre de archivo especificados:
  
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

Ninguna. El cmdlet Search-CcLog no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

